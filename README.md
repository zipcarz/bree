bree
====

<!doctype html>  
<html lang="en">  
<head>  
  <meta charset="utf-8">  
  <title>jQuery.extend demo</title>  
  <script src="//code.jquery.com/jquery-1.10.2.js"></script>  
</head>  
<body>  
   
<div id="log"></div>  
   
<script>  
var object1 = {  
  apple: 0,  
  banana: { weight: 52, price: 100 },  
  cherry: 97  
};  
var object2 = {  
  banana: { price: 200 },  
  durian: 100  
};  
   
// Merge object2 into object1  
$.extend( object1, object2 );  
   
var printObj = typeof JSON !== "undefined" ? JSON.stringify : function( obj ) {  
  var arr = [];  
  $.each( obj, function( key, val ) {  
    var next = key + ": ";  
    next += $.isPlainObject( val ) ? printObj( val ) : val;  
    arr.push( next );  
  });  
  return "{ " +  arr.join( ", " ) + " }";  
};  
   
$( "#log" ).append( printObj( object1 ) );  
</script>  
   
</body>  
</html>  
