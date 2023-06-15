---
title:  "Building GUI with C++"
date:   2023-06-14 21:46:52 -0500
header:
  teaser: /assets/images/GUI_CPP.png
categories: tools
tags: c++ rest html css js
---

# Introduction
When I got my first tech gig working as an IT Specialist for a small business,
I needed to create a way for me to save my hours worked when I was working from home.
After spending a few days researching different GUI libraries in C++, I couldn't
find one that was quick and easy to use. Then it finally hit me, while I was
looking into how I could build a more private version of Discord. Why not tie
HTML/CSS, javascript, and CSS together using a restAPI. This would allow me 
to create an app that could be ported over to any device. Although this isn't 
a new discovery, I thought it would be pretty cool to write about.

# Creating the API
To do this, all we have to do is use [restbed](https://github.com/Corvusoft/restbed),
a C++ RESTful library. With restful we can create a bridge between our web server and C++.
When someone wants to view a webpage, we can return the HTML for that page, and when someone wants to
call an API command, we can handle that request accordingly.
## Crude Example
```cpp
#include <iostream>
#include <memory>
#include <string>
#include <fstream>
#include <sstream>
#include <restbed>

std::string file_to_string(std::string path){
	std::fstream file(path, std::ios_base::in);
	std::stringstream ss;
	ss << file.rdbuf();
	return ss.str();
}

void time_clock_page_handler(const std::shared_ptr<restbed::Session> session) {
	std::string page = file_to_string("html/TimeClock.html");
	session->close(restbed::OK, page, /* Ommited because jekyll doesn't like to parse the header */);
}

int main() {

	auto TimeClock = std::make_shared<restbed::Resource>();
	TimeClock->set_path("/");
	TimeClock->set_method_handler("GET", time_clock_page_handler);

	auto settings = std::make_shared<restbed::Settings>();
	settings->set_port(80);

	restbed::Service service;
	service.publish(TimeClock);
	service.start(settings);
	return EXIT_SUCCESS;
}
```

# Creating an application
Once the Web app has been created, all we have to do is create a web view application
for the platforms we which to support.

# Why do this?
When creating an application for multiple platforms it's always difficult, and time-consuming
to write code for every platform. It also becomes cumbersome to make any change to the GUI, 
as you end up having to debug and rewrite the GUI for different platforms. With this method though,
we can make quick changes to our webpage, and, with a responsive design, the changes
are made to all platforms.

# Conclusion
Building a responsive webpage is much more simple to do, compared to creating a native
gui with C++. By utilizing restbed, you can create links between a webpage and C++. Allowing
for a more responsive, better-looking, and functional application with cross-platform support.
