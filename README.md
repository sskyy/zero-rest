# zero-rest #

Automatically generate REST api for model which has attribute `rest`.

## Usage ##

1. Add dependency to your module package.json file like:

```
{
	"name" : "YOUR_MODULE_NAME",
	"zero" : {
		"dependencies" : {
			"rest" : "^0.0.1"
		}
	}
}
```

2. mark your model as:

```
module.models = [{
    identity : 'post',
    rest : true
},{
    identity : 'user',
    rest : ['find','findOne']
}]
```

With `rest:true` as the post model above, rest module will generate `GET /post`, `GET /post/:id`, `POST /post`, `PUT /post/:id` and `DELETE /post/:id` for post model.
With `rest:[]` as user model, rest will only generate `GET /user`, `GET /user/:id`. Below is the mapping for action and url:

```
find : GET /model
findOne : GET /model/:id
create : POST /model
put : UPDATE /model/:id
destroy : DELETE /model/:id
```
