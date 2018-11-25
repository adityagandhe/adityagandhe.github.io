---
layout: post
<<<<<<< HEAD
title: JSOM
subtitle: Site operations
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [JSOM,ClientSide]
comments: true




## Here is a secondary heading

Here's a useless table:

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |


How about a yummy crepe?

![Crepe](http://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg)

Here's a code chunk:
<input title="siteName" id="siteName" type="text"/><input id="fetchSite" onclick="GetSiteInfo()" type="button" value="Fetch Site"/>
<input id="createSite" onclick="CreateSite()" type="button" value="CreateSite"/>
<input id="UpdateSite" onclick="Update()" type="button" value="UpdateSite"/>
<input id="DeleteSite" onclick="Delete()" type="button" value="DeleteSite"/> ​ 
<div id="displaydata">
</div>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script><script type="text/javascript">
    var ctx;
var website;
var website1;
var displayData;
var webCollection ;
var webCollection1 ;
//Delete

function Delete()
 {
     ctx = new SP.ClientContext.get_current();

    website1=ctx.get_web() ;
 
 

  webCollection1 = website1.getSubwebsForCurrentUser(null);


ctx.load(webCollection1);

 
 ctx.executeQueryAsync(SuccessDelete,FailureDelete)

     
 }
 function SuccessDelete()
 {

  

var webEnumerator = webCollection1 .getEnumerator();
   while (webEnumerator.moveNext())
 {
var current= webEnumerator.get_current()
          
           displayData = current.get_title() ;
    if (displayData ==$("input[title^='siteName']").val())
 {
     
   current.deleteObject();
alert("deleted");
   }

}

 ctx.executeQueryAsync(SuccessDeleteConfirm,FailureDeleteConfirm)
    }
    
    function SuccessDeleteConfirm()
    {
    alert("deleted");
    }
     function FailureDeleteConfirm()
     {
     
     alert("deleted failed");
     }
    function FailureDelete(sender, args)
 {
     alert("Error" + args.get_message());

   }

//Update
function Update()
 {
     ctx = new SP.ClientContext.get_current();

    website1=ctx.get_web() ;
 
 

  webCollection1 = website1.getSubwebsForCurrentUser(null);


ctx.load(webCollection1);

 
 ctx.executeQueryAsync(SuccessUpdate,FailureUpdate)

     
 }
 function SuccessUpdate()
 {
     alert("updated");
  
 var count=webCollection1.get_count();
var webEnumerator = webCollection1 .getEnumerator();
   while (webEnumerator.moveNext())
 {
var current= webEnumerator.get_current()
          
           displayData = current.get_title() ;
    if (displayData ==$("input[title^='siteName']").val())
 {
     current.set_title("Update");
   current.update();

   }

}

 ctx.executeQueryAsync(Success,Failure)
    }
    
    function Success()
    {
    alert("updated");
    }
     function Failure()
     {
     
     alert("fail");
     }
    function FailureUpdate(sender, args)
 {
     alert("Error" + args.get_message());

   }


  function GetSiteInfo()
{
      ctx = new SP.ClientContext.get_current();

    website=ctx.get_web();
    //ctx.loadQuery(website);
    //ctx.load(website, 'Title', 'Created');
    webCollection = website.getSubwebsForCurrentUser(null);
    ctx.load(webCollection);
    
    
    ctx.executeQueryAsync(SuccessSite,FailureSite)
    
    }
    function SuccessSite()
    
{$('#displaydata').empty();
    var webEnumerator = webCollection .getEnumerator();
    while (webEnumerator.moveNext()){
var current= webEnumerator.get_current()
    
    displayData = current.get_title() ;
$('#displaydata').append(displayData + "<br />"+"</n>");
}
alert("DisplayData" + displayData);

}
function FailureSite(sender, args) {
  alert("Error" + args.get_message());
}

function CreateSite() {
  alert("sitename" + $("input[title^='siteName']").val());
  ctx = new SP.ClientContext.get_current();

  website = ctx.get_web();


  ctx.load(website);
  var title = $("input[title^='siteName']").val();
  var siteCreation = new SP.WebCreationInformation();
  siteCreation.set_title(title);
  siteCreation.set_description('new subsite for test');
  siteCreation.set_useSamePermissionsAsParentSite(true);
  siteCreation.set_language(1033);
  siteCreation.set_url(title);
  website.get_webs().add(siteCreation);
  website.update()
  ctx.executeQueryAsync(SuccessSiteCreation, FailureSiteCreation)

}

function SuccessSiteCreation() {

  alert("site is created");
}

function FailureSiteCreation() {
  alert("site is failed");

}
</script>


var foo = function(x) {
  return(x + 5);
}
foo(3)
~~~

And here is the same code with syntax highlighting:

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.
=======
Coming Soon
