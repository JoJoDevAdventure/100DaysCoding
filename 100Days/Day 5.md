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

## What I want to learn :
