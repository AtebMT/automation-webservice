var http = require('http');
var express = require('express');

var app = express();
app.set('port', process.env.PORT || 3000);

app.get('/', function (req, res) {
  res.send('<html><body><h1>Hello World</h1></body></html>');
});

app.get('/hello/:a?', function (req,res) {
	res.set('Content-Type','application/json');
	var result = {};
	result.Greeting = "Hello";
	result.Name = req.params.a;
	res.send(200, result);
});

http.createServer(app).listen(app.get('port'), function(){
  console.log('Express server listening on port ' + app.get('port'));
});
