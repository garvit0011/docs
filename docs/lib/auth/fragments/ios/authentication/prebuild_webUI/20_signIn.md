Now you are ready to invoke the signIn webUI, the api require a presentationAnchor and for an iOS app it will be the main UIWindow of the app. The example code below assume that you are in a UIViewController where you can fetch the UIWindow instance by `self.view.window`.

```swift
func signInWithWebUI() {
    _ = Amplify.Auth.signInWithWebUI(presentationAnchor: self.view.window!) { result in
        switch result {
        case .success(_):
            print("Sign in succeeded")
        case .failure(let error):
            print("Sign in failed \(error)")
        }
    }
}
```