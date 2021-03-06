---
title: Processors


layout: post
date: 2018-08-17 01:23:59 +0000
tags:
- server-side-api
url: "/processors/"
aliases:
- "/GlideScriptedProcessor/"
- "/GlideServletRequest/"
- "/GlideServletResponse/"
---
# GlideServlet aka Processors
<!--more-->

# GlideScriptedProcessor

| Property/Method | Description |
| --- | --- |
| redirect | Redirects to the specified URL |
| writeOutput | Writes the contents of the given string to the response |
| writeJSON | Writes a JSON object to the current URL. Note: Works only in scoped apps |


## GlideServletRequest

| Property/Method   | Description                                     |
| ----------------- | ----------------------------------------------- |
| getHeaders        | Returns an array of headers as a string         |
| getHeaderNames    | Returns an array of header names as a string    |
| getQueryString    | Returns the query string from the request       |
| getContentType    | Returns the content type                        |
| getParameterNames | Returns an array of parameter names as a string |
| getHeader         | Returns the header                              |
| getParameter      | Returns an object                               |

## GlideServletResponse

| Property/Method | Description                                   |
| --------------- | --------------------------------------------- |
| setContentType  | Sets the MIME type of the response            |
| sendRedirect    | Sends a temporary redirect to the client      |
| setStatus       | Sets the status code for the response         |
| setHeader       | Sets a response header to the specified value |