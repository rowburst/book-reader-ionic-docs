# Book Reader Ionic 3 App - Developer Docs
The app Book Reader contains a complete Workflow and User Experience for a book reading app and is ready for release. You just need to customize it for your needs, add your books, logos, edit package name and publish it. The app incorporates a beautiful design soothing to eyes of the reader.
You can browse list of available books, their authors, descriptions and categories. Read PDF books online, Save and download books that you like offline. It uses ionic-storage and Phone's disk for storing downloaded books. The App uses internet connection to authenticate and to fetch list of books.

## Installation
NodeJs 8.x or above must be installed on your system.

Open command line. If Ionic & Cordova are not already installed, install them via
```sh
$ npm install -g ionic cordova
```
Run the project
```sh
$ cd ionic-project
$ npm install
$ ionic serve
```
In your browser, you can go to http://localhost:8100 and view the ionic app.

To run on android and debug
```sh
$ ionic cordova run android --debug --consolelogs --livereload
```

## Design - Theming
Change the value of colors in `$colors` variable in variables.scss file at src/theme/variable.scss to change the theme of app.

## Pages
* login: Shows the login form. It uses UsersProvider to call and Authenticate via REST APIs. Currently contains just an example.
* signup: Shows sign up form. Must use UsersProvider to register user.
* tabs: After login, it becomes the Root Page of app. Contains "books", "my-books" pages.
* books: uses BooksProvider to fetch the books from REST APIs and shows them. You can search the books on this page. 
* book-detail: On clicking "Read" button on books page, this page opens and shows the details and download/read buttons.
* my-books: shows the books saved and downloaded by users. It uses `ionic-storage` for remembering the location of the downloaded books. It uses `@ionic-native/file-transfer` & `@ionic-native/file` for saving the PDF file phone's storage.
* book-detail-local: shows the details of single book, saved locally. Allows to delete the book from `ionic-storage` & from phone disk.
* about: Put your organization's mission/description.
* help: Put your privacy policy and some usage details for user.
* pdf-viewer: Makes it possible to view the PDF book online and offline.

## Providers - (Angular 5 Services)
* BooksProvider: Fetches data from REST APIs. Uses [static-api-at-rowburst](https://github.com/rowburst/static-api-at-rowburst) project's Books APIs.
* UsersProvider: Contains an example of Http POST request. This provider must be used for login, signup and other user related network calls.

## Prepare for Release
* Integrate you REST APIs. (You can also use GitHub to serve as REST APIs like we did. But its not recommended. Because it's public and cannot be used as full backend hosting.)
* Test Authentication
* Add your assets, icons and package name in `config.xml`
* Build for release using Ionic Docs (https://ionicframework.com/docs/intro/deploying)

## Ads
Ads are not integrated by default. But enough space is left intentionally on 
* book-detail Page
* book-detail-local Page
* Side Menu
to show ads.If you place ads at the above mentioned places, they won't interfere with user experience.

But with free version of [AdMob Pro](https://ionicframework.com/docs/native/admob-pro/) you can easily show ads other places as well.

## Found Bug
If you find any bug, you can contact me at emadulehsan@gmail.com. Set the Subject of email to [BOOK READER - CODECANYON]

## End Note
Thank you for giving Book Reader a try. You can connect with me at [@e_mad_ehsan](https://twitter.com/e_mad_ehsan)

Happy Coding :)

PS: You can read this documentation in a beautiful way here: https://github.com/rowburst/book-reader-ionic-docs
