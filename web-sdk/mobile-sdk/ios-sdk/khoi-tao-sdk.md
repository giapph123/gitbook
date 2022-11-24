# Khởi tạo SDK

Đối với IOS Omicall cung cấp cài đặt cho 2 môi trường kiểm thử ( Sanbox ) và triển khai  ( Production )

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Cấu hình các chứng chỉ cho từng môi trường phát triển trên Omicall</p></figcaption></figure>

Chúng ta cần import lớp thư viện để bắt đầu

```objectivec
#import <OmiKit/OmiKit.h>
```

## Bước 1: cài đặt môi trường:&#x20;

```objectivec

[OmiClient setEnviroment:KEY_OMI_APP_ENVIROMENT_SANDBOX];
có 2 biến môi trường:
- KEY_OMI_APP_ENVIROMENT_SANDBOX
- KEY_OMI_APP_ENVIROMENT_PRODUCTION
```

## Bước 2: Cài đặt lớp xử lý Voip Push :&#x20;

```objectivec
provider = [[CallKitProviderDelegate alloc] initWithCallManager: [OMISIPLib sharedInstance].callManager ];
voipRegistry = [[PKPushRegistry alloc] initWithQueue:dispatch_get_main_queue()];
pushkitManager = [[PushKitManager alloc] initWithVoipRegistry:voipRegistry];
```

## Bước 3: Cài đặt xử lý Push notification:

```objectivec
- (void)requestPushNotificationPermissions
{
    // iOS 10+
    UNUserNotificationCenter *center = [UNUserNotificationCenter currentNotificationCenter];
    [center getNotificationSettingsWithCompletionHandler:^(UNNotificationSettings * _Nonnull settings) {
        switch (settings.authorizationStatus)
        {
            // User hasn't accepted or rejected permissions yet. This block shows the allow/deny dialog
            case UNAuthorizationStatusNotDetermined:
            {
                center.delegate = self;
                [center requestAuthorizationWithOptions:(UNAuthorizationOptionSound | UNAuthorizationOptionAlert | UNAuthorizationOptionBadge) completionHandler:^(BOOL granted, NSError * _Nullable error)
                 {
                     if(granted)
                     {
                         dispatch_async(dispatch_get_main_queue(), ^{
                             [[UIApplication sharedApplication] registerForRemoteNotifications];
                         });
                     }
                     else
                     {
                         // notify user to enable push notification permission in settings
                     }
                 }];
                break;
            }
            case UNAuthorizationStatusAuthorized:
            {
                dispatch_async(dispatch_get_main_queue(), ^{
                    [[UIApplication sharedApplication] registerForRemoteNotifications];
                });
                break;
            }
            default:
                break;
        }
    }];
}

- (void)application:(UIApplication*)app didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)devToken
{
    // parse token bytes to string
    const char *data = [devToken bytes];
    NSMutableString *token = [NSMutableString string];
    for (NSUInteger i = 0; i < [devToken length]; i++)
    {
        [token appendFormat:@"%02.2hhX", data[i]];
    }
    [OmiClient setUserPushNotificationToken:[token copy]];
}


```



## Bước 4: Khởi tạo thư viện

```objectivec
    [OmiClient initWithUsername:@"xx" password:@"xx" realm:@""];
    [OmiClient startOmiService];
```
