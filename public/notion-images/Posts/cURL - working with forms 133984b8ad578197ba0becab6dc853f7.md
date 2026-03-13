# cURL - working with forms

Date: 10/04/2019
Tags: Terminal, Tools, cURL

In the first cURL [post](cURL%20-%20Command%20line%20URL%20tool%20133984b8ad57815ab271fc8845e903e0.md), I wrote about how to download files using cURL. I recently got an opportunity to work with forms using cURL. In this post, I will describe how I used cURL to send a POST request to page containing a form. The objective was to obtain the response from the server after submitting a form. The form contained three text boxes with id’s that could be used to submit the form using cURL. The man page for cURL has plenty of options that can be used to get this done. Hence going through the man page is highly recommended.

The default request cURL performs is a POST request and hence it is not required in our code. However, it can be mentioned using `-X` option, to change in case of GET requests. (I like mentioning it, so that I know what has to be done in case of GET requests!) In order to submit data along with our request, we need to use `--data` or `-d` option to specify the fields, which can be separated by an `&` symbol and written together. If the data you want to insert contains special characters, you can use `--data-urlencode` option for that particular field. Assuming the three text boxes on a webpage are id, name and age, the curl command will look like this:
`curl <http://website.com/page.php> -X POST --data "id=1" -d "name=Bob&age=15"`

The server responds with a success message informing the data has been stored. If the server also requires you pass a cookie in order to perform this action, you can do so using the `-b` option for raw cookie data. If two cookies are required, it should be in the format “cookie1=data1; cookie2=data2” If the `=` symbol is not used, it will treat that as filename where cookie details are specified.
`curl <http://website.com/page.php> -X POST -d "id=1" -d "name=Bob&age=15" -b "auth=user"`

There are plenty of options with cookies including files, that are received from the server or a file that is being sent from the client side. In such cases, cookies can also be specified using the `-c` option. As mentioned earlier, going through the `man` page comes in handy when you want to learn explore more on a particular argument or flag options.

Hope some of these comes in handy to you when working with forms and playing around with cURL.

---

[🏠](../../Welcome%20to%20ZyBlog%20133984b8ad578073b4b6e62800ce71c3.md)

---