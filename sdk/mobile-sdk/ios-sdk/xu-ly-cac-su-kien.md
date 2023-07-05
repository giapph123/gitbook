# Xử lý các sự kiện

## Notification callback

### Call notification:

#### 1. To listen event of Call we setting notification:

```
   [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(callStateChanged:) name:OMICallStateChangedNotification object:nil];
```

Declare function Listen event Call State to know when call confirm or invite state: Notification key: OMICallStateChangedNotification Example

```
- (void)callStateChanged: (NSNotification *)notification {
   
   __weak typeof(self)weakSelf = self;
   dispatch_async(dispatch_get_main_queue(), ^{
       __weak  OMICall *call = [[notification userInfo] objectForKey:OMINotificationUserInfoCallKey];
       switch(call.callState)
       {
           case OMICallStateEarly:
               OMILogDebug(@"callStateChanged OMICallStateEarly : %@",call.uuid.UUIDString);
               break;
           case OMICallStateCalling:
               OMILogDebug(@"callStateChanged OMICallStateCalling : %@",call.uuid.UUIDString);
               break;
           case OMICallStateIncoming:{
               OMILogDebug(@"callStateChanged OMICallStateIncoming : %@",call.uuid.UUIDString);
               break;
           }
           case OMICallStateConnecting:
               OMILogDebug(@"callStateChanged OMICallStateConnecting : %@",call.uuid.UUIDString);
               break;
           case OMICallStateConfirmed:{
               OMILogDebug(@"callStateChanged OMICallStateConfirmed : %@",call.uuid.UUIDString);
              
               break;
           }
           case OMICallStateDisconnected:
               OMILogDebug(@"callStateChanged OMICallStateDisconnected : %@",call.uuid.UUIDString);
               break;
       }
   });
}
```

#### 2. Listen event Media event:

Notification key: OMICallMediaStateChangedNotification Example:

```
- (void)callMediaStateChanged: (NSNotification *)notification {
    
    __weak typeof(self)weakSelf = self;
    dispatch_async(dispatch_get_main_queue(), ^{
        OMICallMediaState mediaState = (OMICallMediaState)[[notification userInfo] objectForKey:OMINotificationUserInfoCallMediaStateKey];
        switch(mediaState)
        {
            case OMICallStateMuted:
                OMILogDebug(@"OMICallMediaState OMICallStateMuted");
                break;
            case OMICallStateToggleSpeaker:
                OMILogDebug(@"OMICallMediaState OMICallStateToggleSpeaker");
                break;
            case OMICallStatePermissionCameraDenied:
                OMILogDebug(@"OMICallMediaState OMICallStateToggleSpeaker");
                break;
            case OMICallStatePermissionMicrophoneDenied:
                OMILogDebug(@"OMICallMediaState OMICallStateToggleSpeaker");
                break;
            
        }
    });
}
```

#### 3. Listen event call misscall:

```
[Omiclient setMissedCallBlock:^(OMICall * _Nonnull __weak call) {
        <#code#>
}];
```

#### 4. Listen the Video call state

when event come we need to re-render video screen Detail sample project can view here: [https://github.com/VIHATTeam/IOS-Objective-VideoCall-Example](https://github.com/VIHATTeam/IOS-Objective-VideoCall-Example)

```
### Listen: 
```

````
    [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(videoNotification:) name:OMICallVideoInfoNotification object:nil];
    ```
    ### Process: 
```ruby
    -(void) videoNotification:(NSNotification *) noti {
        NSDictionary *dic = [noti userInfo];
        NSNumber * state = [dic valueForKey:OMIVideoInfoState];
        switch([state intValue]){
            case OMIVideoRemoteReady:{
                [self startPreview];
                break;
            }
        }
    }
````

```
### Show Video Preview:
```

```
    - (void)startPreview {
        __weak typeof(self) weakSelf = self;
        if(!_remoteVideoRenderView || !_localVideoRenderView) return;
        
            dispatch_async(dispatch_get_main_queue(), ^{
                weakSelf.remoteVideoRenderView.contentMode = UIViewContentModeScaleAspectFill;
                [weakSelf.remoteVideoRenderView setView:[self.videoManager createViewForVideoRemote:weakSelf.remoteVideoRenderView.frame]];
                weakSelf.localVideoRenderView.contentMode = UIViewContentModeScaleAspectFill;
                [weakSelf.localVideoRenderView setView:[self.videoManager createViewForVideoLocal:weakSelf.localVideoRenderView.frame]];
            });
    }
```

#### 5. Listen the network health for update UI instruction for user

The information we calculator on MOS score and device 3 level bellow

```
    Listen: 
    [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(updateNetworkHealth:) name:OMICallNetworkQualityNotification object:nil];
    
    Process: 
    
    -(void) updateNetworkHealth:(NSNotification *) noti {
        NSDictionary *dic = [noti userInfo];
        NSNumber * state = [dic valueForKey:OMINotificationNetworkStatusKey];
        switch([state intValue]){
            case OMINetworkGood:{
                [self.networkStatus setImage: [UIImage imageNamed: @"network_best"]];
                break;
            }
            case OMINetworkMedium:{
                [self.networkStatus setImage: [UIImage imageNamed: @"network_medium"]];
                break;
            }
            case OMINetworkBad:{
                [self.networkStatus setImage: [UIImage imageNamed: @"network_bad"]];
                break;
            }
        }
    }
```

\
