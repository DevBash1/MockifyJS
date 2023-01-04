# MockifyJS
MockifyJS is an npm package that allows you to quickly create a mock server by using a very easy to learn and understand syntax.

# Install
MockifyJS can be installed with npm using the command below.

```
npm i -g mockifyjs
```

# Usage
After Installing MockifyJS,   
Create a mocker file ```server.mkr```,   
and run your mocker file with the command

```
mockify server.mkr
```

Which will run the mocker file on the default Port ```3000```   
You can change this by passing the port too.

```
mockify server.mkr 5000
```

Modifying a mocker file after runing the mocker server will make the changes take place instantly,   
Which means you dont have to restart the mocker server everytime you modify the mocker file.   

# Syntax

The Mocker Syntax is very easy to understand and learn.   
This is a basic mocker file syntax.

![alt="MockifyJS"](https://github.com/DevBash1/MockifyJS/raw/main/MockifyJS.jpg)

A Mocker File has a ```Request Method``` which could be any of this.    
* GET - a GET request
* POST - a POST request
* PUT - a PUT request
* DELETE - a DELETE request
* HEAD - a HEAD request
* OPTIONS - a OPTIONS request
* TRACE - a TRACE request
* CONNECT - a CONNECT request
* ALL - any type of request    

## Request Path

The `Request Path` is the Request Path of a request.   
Eg `api/v2/user`,`password/forgot`,etc    


When any request to the mocker server matches the `Request Method` and `Request Path`,   
The `Response Headers` and `Response Text` is returned.   
If the request does not match any request in the mocker file, a `404` error occurs.

## Tags
Mocker Tags are special words in `MockifyJS` which starts with a `$`,   
We use these Tags in The `Response Text` to return a special type of response.

![alt="MockifyJS"](https://github.com/DevBash1/MockifyJS/raw/main/mockifyjs.png)

### echo
The echo Tag simply returns the `Request Data` as the `Response Text`,   
Which means it gives you back what you give it.

```js
POST /api 200
    Content-Type: application/json
$echo
```

### randNumber
The randomNumber Tag takes a number and returns a random number between 0 and the number passed to it.

```js
POST /random 200
    Content-Type: application/json
$randNumber 100
```

### get
The get Tag takes a url and makes a get request to this url and retun the response as `Response Text`

```js
POST /get/example 200
$get https://example.com
```

### readFile
The readFile Tag reads a file from the file system and return it as the `Response Text`   
This can be used to return a media or any other type of file.   
This is an example of an image file.   

```js
GET /images/cat.jpg 200
    Content-Type: image/jpeg
$readFile ../../Downloads/cat.jpg
```

**MockifyJS** was made with ❤️ in 🇳🇬 by [Dev Bash](https://github.com/DevBash1)
