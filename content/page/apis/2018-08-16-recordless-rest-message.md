---
title: Recordless Rest Message
date: 2018-08-16



layout: post
tags:
 - server-side-api
url: "/rest/"
aliases:
- "/rest/"
- "/Outbound-REST-Message-Example/"
---
I often use the recordless rest calls to test things.  I didn’t see it  on my blog, so here’s an example so I can find it in the future.  
<!--more-->

```js
    var instance = "dev40379";
    var requestBody = {
        short_description: "test incident"
    };
    var restMessage = new sn_ws.RESTMessageV2();
    restMessage.setBasicAuth("slack", "slack");
    restMessage.setHttpMethod("post");
    restMessage.setEndpoint("http://"+ instance +".service-now.com/api/now/table/incident");
    restMessage.setRequestBody(JSON.stringify(requestBody));
    var response = restMessage.execute();
    var error = response.haveError();
    if(error){
    var errorCode = response.getErrorCode();
    var errorMsg = response.getErrorMessage();
    } else {
    }
    var headerVal = response.getHeader("Content-Type");
    var headers = response.getHeaders();
    var queryString = response.getQueryString();
    var statusCode = response.getStatusCode();
    var responseBody = response.getBody();
    gs.info(statusCode);
    gs.info(responseBody);
    /**
     * *** Script: 201
     * *** Script: {"result":{"parent":"","made_sla":"true","caused_by":"","watch_list":"","upon_reject":"cancel","sys_updated_on":"2017-11-15 20:56:39","child_incidents":"0","hold_reason":"","approval_history":"","skills":"","number":"INC0010006","resolved_by":"","sys_updated_by":"slack","opened_by":{"link":"https://dev40379.service-now.com/api/now/table/sys_user/f3bfdeb14f12030002b3f2318110c7f8","value":"f3bfdeb14f12030002b3f2318110c7f8"},"user_input":"","sys_created_on":"2017-11-15 20:56:39","sys_domain":{"link":"https://dev40379.service-now.com/api/now/table/sys_user_group/global","value":"global"},"state":"1","sys_created_by":"slack","knowledge":"false","order":"","calendar_stc":"","closed_at":"","cmdb_ci":"","delivery_plan":"","impact":"3","active":"true","work_notes_list":"","business_service":"","priority":"5","sys_domain_path":"/","rfc":"","time_worked":"","expected_start":"","opened_at":"2017-11-15 20:56:39","business_duration":"","group_list":"","work_end":"","caller_id":"","resolved_at":"","approval_set":"","subcategory":"","work_notes":"","short_description":"test incident","close_code":"","correlation_display":"","delivery_task":"","work_start":"","assignment_group":"","additional_assignee_list":"","business_stc":"","description":"","calendar_duration":"","close_notes":"","notify":"1","sys_class_name":"incident","closed_by":"","follow_up":"","parent_incident":"","sys_id":"98266e404f22030002b3f2318110c705","contact_type":"","incident_state":"1","urgency":"3","problem_id":"","company":"","reassignment_count":"0","activity_due":"","assigned_to":"","severity":"3","comments":"","approval":"not requested","sla_due":"","comments_and_work_notes":"","due_date":"","sys_mod_count":"0","reopen_count":"0","sys_tags":"","escalation":"0","upon_approval":"proceed","correlation_id":"","location":"","category":"inquiry"}}
     */
```