# Day 6

## What I Learned :

• well today I learned unit testing, Finally yes

some of the tests that I wrote :

First I initialized a Service that I wanted to test 

```
  var signUp: LoginService!
```

Then start and setup

```
    override func setUp() {
        super.setUp()
        signUp = AuthManager()
    }
    
    override func tearDown() {
        signUp = nil
        super.tearDown()
    }
```

and here's what a test should look like 

```
    func test_email_is_badly_formated_password_empty() async {
        do {
            try await signUp.loginUserWith(email: "youssef", password: "")
            XCTAssert(user == nil)
        } catch {
            // verify that we got the correct error
            XCTAssert(error as! LoginErrors == LoginErrors.emailNotFormated)
        }
    }
```

• I learned how to do animations using the scroll view offset

## What I accomplished :

• I cleaned up my macbook

• I created a cool animation in [iCookPad app](https://github.com/JoJoDevAdventure/iCookPad)

###### here's what it looks like :

https://user-images.githubusercontent.com/89042174/172746311-78be2e39-62d6-498d-9eb2-13b9989078fe.mp4

• I finished SignIn Unit tests

## What I want to learn :

- [ ] learn about UI testing
- [ ] Fix UI in the details VC
- [ ] Learn more functionalities in SDWeb
