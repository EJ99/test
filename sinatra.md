#Request/Response

* Server waits for request and gives a response.
* Browser doesn't understand embedded ruby, only understands html, css, js.
* So server will convert embedded ruby into html and send html file to client.
* Every request/response is considered new, doesn't remember request before
* get/donate is a request - so a query string is an extra request/atrribute
* stored as a key value pair - stored in params
* form element is the other way of sending info to the server
* when you send something to the server it goes to params
* but what if you want a banner on every erb page
* layout is a special template page
* to connect the layout page with the other pages put <%= yield = %> in the layout.erb
* this grabs the information from the other pages
* put banners, logos, index etc in layout.erb
* get rid of button type when using in forms in ruby




```
[1] pry(#<Sinatra::Application>)> params
=> {"num1"=>"2", "num2"=>"1", "button"=>""}
[2] pry(#<Sinatra::Application>)> params[:num1]
=> "2"
[3] pry(#<Sinatra::Application>)> params[:num1].to_i + params[:num2].to_i
=> 3
[4] pry(#<Sinatra::Application>)>
```
