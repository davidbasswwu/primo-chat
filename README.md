primo-chat
==========

How we added Springshare chat to our instance of Primo
<br>David Bass @ WWU
<br>21 Aug 2014

To add Springshare chat to Primo (as shown in thes screenshot below), we added the following code to our Primo footer (http://library.wwu.edu/info/primo/wwu_footer.html).  To see our code, just view source, and search for "chat".

![](https://dl.dropboxusercontent.com/u/139438694/ShareX/2014-08/2014-08-21_13-46-12.png)

Here is a simplified version of what you need to make this work:

```
<script> 
$(document).ready(function() {
	var libchat_btn = {
	   iid: "your-id-here",
	   key: "your-key-here",
	   domain: "askus.library.example.edu",
	   splash: "Welcome to My University Chat!",
	   button_online: "http://library.example.edu/images/chat_on.png",
	   button_offline: "http://library.example.edu/images/chat_off.png",
	   offline_url: "http://askus.library.example.edu/browse.php?tid=23567",
	   question: "Please enter question below:",
	   star_ratings: true,
	   star_text: "Please rate this chat:",
	   depart_id: "your-depart-id-from-springshare"
	};

	// replace the contactalibrarian div with the Springshare Chat
	$("#exlidSearchBanner").html("<div id='libchat_btn_widget'></div>");
});
</script>

<script type="text/javascript" src="//libanswers.com/js/chat_load_client.js"></script>

```

The basic concept is to:
 - Define your libchat parameters (see the "var libchat_btn" section)
 - Create a place for your widget to go into (see the " replace the contactalibrarian div with the Springshare Chat" section)
 - And then when the libanswers.com/js/chat_load_client.js is loaded (see our footer for the code), it will magically appear. 

Please note that this code requires jQuery, but it is already loaded by Primo.

Hope this helps.  :)
