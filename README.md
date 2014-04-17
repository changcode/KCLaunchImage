Fake-ZhiHu-Daily-LaunchImage-Transition
=======================================
## Installation

1. Add `KCLaunchImageViewController.h` and `KCLaunchImageViewController.m` into your project
2. Create a new image set named `FakeLaunchImage`
3. Add your own launch image into `LaunchImage` and `FakeLaunchImage` separately
4. Add your own display image named `displayImage`
4. In your `AppDelegate.m` file, add those code

```objective-c
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    UIImageView *splashScreen = [[UIImageView alloc] initWithImage:[UIImage imageNamed:@"FakeLaunchImage"]];
    [self.window addSubview:splashScreen];

    self.window.rootViewController =
    [KCLaunchImageViewController addTransitionToViewController:[[KCViewController alloc] init]
                                          modalTransitionStyle:UIModalTransitionStyleCrossDissolve
                                                     withImage:@"displayImage" // your own display image
                                                     taskBlock:^(void){
                                                         [splashScreen removeFromSuperview];
                                                     }];

    return YES;
}
```
## Author

kavichen, chen1qi2wei3@gmail.com

## License

FakeZhiHuDailyLaunchTransition is available under the MIT license. See the LICENSE file for more info.
