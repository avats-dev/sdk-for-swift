```swift
import Appwrite

func main() {
    let client = Client()
      .setEndpoint("https://[HOSTNAME_OR_IP]/v1") // Your API Endpoint
      .setProject("5df5acd0d48c2") // Your project ID

    let projects = Projects(client: client)
    projects.updateAuthStatus(
        projectId: "[PROJECT_ID]",
        method: "email-password",
        status: xfalse
    ) { result in
        switch result {
        case .failure(let error):
            print(error)
        case .success(let response):
            let json = response.body!.readString(length: response.body!.readableBytes)
        }
    }
}
```