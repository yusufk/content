<!--
date: '2008-10-21'
published: true
slug: 2008-10-how-to-add-news-bar-onto-your-wordpress
time_to_read: 5
title: How to add a News Bar onto your wordpress blog..
-->

Thought I'd share how I managed to get the Google Ajax News Bar you hopefully see at the top of the page...  
  
1stly, visit [this site](http://www.google.com/uds/solutions/wizards/newsbar.html?uds_o=1 "this site") to obtain the necessary code..  
  
Then, open you WP-ADMIN page and cick on Design -- Theme Editor  
  
Click on the Header template.  
  
Once loaded, insert the following lines from the Ajax code (cut from the generated code) right at the bottom of the header file (below the <hr /> tag):  
> ```
>         <div id="newsBar-bar">
> ```
>
>   
>
> ```
>                <span style="color:#676767;font-size:11px;margin:10px;padding:4px;">Loading...</span>
> ```
>
>   
>
> ```
>         </div>
> ```

  
And insert the other stuff just before the </head> tag:  
> ```
>  <script src="http://www.google.com/uds/api?file=uds.js&v=1.0&source=uds-nbw"  
>     type="text/javascript"></script>  
>   <style type="text/css">  
>     @import url("http://www.google.com/uds/css/gsearch.css");  
>   </style>  
>   
>   <!-- News Bar Code and Stylesheet -->  
>   <script type="text/javascript">  
>     window._uds_nbw_donotrepair = true;  
>   </script>  
>   <script src="http://www.google.com/uds/solutions/newsbar/gsnewsbar.js?mode=new"  
>     type="text/javascript"></script>  
>   <style type="text/css">  
>     @import url("http://www.google.com/uds/solutions/newsbar/gsnewsbar.css");  
>   </style>  
>   
>   <script type="text/javascript">  
>     function LoadNewsBar() {  
>       var newsBar;  
>       var options = {  
>         largeResultSet : false,  
>         title : "In the news",  
>         horizontal : true,  
>         autoExecuteList : {  
>           executeList : ["Islam", "mobile", "science", "universe", "recipes"]  
>         }  
>       }  
>   
>       newsBar = new GSnewsBar(document.getElementById("newsBar-bar"), options);  
>     }  
>     // arrange for this function to be called during body.onload  
>     // event processing  
>     GSearch.setOnLoadCallback(LoadNewsBar);  
>   </script>
> ```
>
>   
> Click on Update and its done!  
>   
> p.s. It takes a few seconds to load the bar, depending on your bandwidth, you should see the word "loading..." as a placeholder.



## 1 comments captured from [original post](https://ysfk.blogspot.com/2008/10/how-to-add-news-bar-onto-your-wordpress.html) on Blogger

**KiLLa said on 2008-10-21**

Thanks for the info<br /><br />Knowledge is always appreciated



[Original post](https://ysfk.blogspot.com/2008/10/how-to-add-news-bar-onto-your-wordpress.html)

#howto #blogging #legacy-blogger 