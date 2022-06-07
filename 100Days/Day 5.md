# Day 5

## What I learned :

• Todat I learned how to use [Alamofire](https://github.com/Alamofire/Alamofire) for the first time

###### Request :

```
let request = AF.request(urlString)

request.validate().responseDecodable(of: ComplexRecipeResponse.self) { [self] (response) in         
     guard let apiResponse = response.value else { return }
}
```

• I learned how to compose a good API Call 

```
struct CustomSearch {
    
    init(origin: String, type: String, diet: String, glutenFree: Bool, vegetarian: Bool, vegan: Bool) {
        if origin != "N/A" {
            self.origin = "&cuisine=" + origin
        }
        if type != "N/A" {
            self.type = "&type=" + type
        }
        if diet != "N/A" {
            self.diet = "&diet=" + diet
        }
        var tags = [String]()
        var stringTag : String = ""
        if glutenFree {
            tags.append("GlutenFree")
        } else if vegetarian {
            tags.append("vegetarian")
        } else if vegan {
            tags.append("vegan")
        }
        tags.forEach { tag in
            if stringTag == "" {
                stringTag += tag
            } else {
                stringTag += ",\(tag)"
            }
        }
        self.tags = "&tags=" + stringTag
    }
    var origin : String?
    var type : String?
    var diet : String?
    var tags : String?
}
```
this api call is made in my [iCookPad](https://github.com/JoJoDevAdventure/iCookPad) app, I'm proud of the avancement, It's moving fast forward.

• I learned to use `lazy var` in UI componment in my view

• I Learned to use `UIScrollView` That I never used before

## What I accomplished :

• I finisehd the custom search ( UI + APICall ) in my cooking app

###### here's what it looks like : 

https://user-images.githubusercontent.com/89042174/172495005-b7f78f12-881b-48e5-adb0-fc3e6a29450a.mp4

• I cleaned up my macbook storage.

• I started the recipe details in [iCookPad](https://github.com/JoJoDevAdventure/iCookPad)

• I used Alamofire to request API.

## What I want to learn :

- [ ] I want to learn how to correcty handle errors
- [ ] Learn how build a clean scroll view
- [ ] How to send photo messages in MessageKit (let's skate app)
- [ ] Algebra revision
