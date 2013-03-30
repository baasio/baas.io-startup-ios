baas.io-startup-ios
===================

처음 사용자를 위한 iOS Startup Project 입니다.

이 프로젝트는 SDK 가 기본 설치되어 있으며, 서버에 데이터 저장을 쉽게 할 수 있도록 기획/제작 되었습니다.

##How To Get Started
### Step 1 : 설정
`@{baas.io ID}`에 baas.io ID를 넣고 단축키 `⌘R`를 눌러 앱을 실행한다.
```objc
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    // 여기!!
    [Baasio setApplicationInfo:@{baas.io ID} applicationName:@"sandbox"];
    
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    // Override point for customization after application launch.
    self.viewController = [[ViewController alloc] init];
    
    //self.window.rootViewController = self.viewController;
    self.window.rootViewController = [[UINavigationController alloc]initWithRootViewController:self.viewController];
    [self.window makeKeyAndVisible];
    return YES;
}
```
baas.io ID는 웹 사이트의 애플리케이션 "기본정보" 화면에서 확인할 수 있다. baas.io ID와 Application ID를 바꾸어 넣지 않도록 주의한다.
위 예시에는 Application ID가 "sandbox"로 입력되어있다. sandbox는 baas.io 회원 가입 시 기본으로 생성되는 백엔드앱이다. Application ID를 바꾸어 테스트하려면, 그 전에 아래 두 문서를 확인하기 바란다.
- [역할과 권한](https://baas.io/docs/ko/devguide/roles.html)
- [baas.io 에서 User Role 설정 기본](http://blog.baas.io/?p=398)

### Step 2 : Test

key/value 를 입력하고 `POST` 버튼을 누른다.


![<create>](https://raw.github.com/wiki/baasio/baas.io-startup-ios/images/create.png)

**foo**라는 Collection에 `{nickname ; @"cetauri"}` 가 성공적으로 입력되었다.

![<query>](https://raw.github.com/wiki/baasio/baas.io-startup-ios/images/query.png)

### Step 3 : 확인
데이터 브라우저에서 위의 입력 내용을 확인 할 수 있다.
![<result>](https://raw.github.com/wiki/baasio/baas.io-startup-ios/images/result.png)

