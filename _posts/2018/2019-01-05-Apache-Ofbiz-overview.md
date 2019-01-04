A kick-starter guide.
This is a personal customized version of Apache's tutorials:
- https://cwiki.apache.org/confluence/display/OFBIZ/OFBiz+Tutorial+-+A+Beginners+Development+Guide

# Tìm gì? ở đâu?

## Viết RESTFull service

> Q: Trong một ứng dụng trên Ofbiz thì các controller được định nghĩa ở đâu?

A: Trong file controller.xml 
.\apache-ofbiz-16.11.05\applications\accounting\webapp\accounting\WEB-INF\controller.xml

> Q: Đọc file controller.xml như thế nào?

<!-- Request Mappings -->
<!-- end of request mappings -->
<!-- View Mappings -->
<!-- Lookup mappings -->
<!-- Assignment Mappings -->
<!-- end of view mappings -->
 
> Q: Có bao nhiêu loại content-type

- screen: xem online trên web (tobe confirmed)
- screenfop: báo cáo dạng giấy A4 (template được định nghĩa chỗ khác)
- screencsv: báo cáo dạng bảng
- screenxml: báo cáo dạng xml

# 1 Hello world (neutron project)

References:
 -  https://cwiki.apache.org/confluence/display/OFBIZ/OFBiz+Tutorial+-+A+Beginners+Development+Guide#OFBizTutorial-ABeginnersDevelopmentGuide-CreateYourFirstApplication(HelloWorld...)

## Creating a plugin

Lúc tạo mới plugin sẽ gặp lỗi kiểu 
```
Could not find resource bundle [PracticeUiLabels] in the locale [en_US]  
Exception: java.lang.IllegalArgumentException  
Message: Could not find resource bundle [PracticeUiLabels] in the locale  
[en_US]
```
Nguyên nhân là do Ofbiz hỗ trợ hiển thị nhiều ngôn ngữ trên giao diện (gọi là UI Labels) nhưng trong trường hợp này không có dòng nào định nghĩa locale là `en_US` nên trang không hiển thị được.
Giải pháp là sửa file: .\apache-ofbiz-16.11.05\specialpurpose\ofbizDemo\config\OfbizDemoUiLabels.xml
chèn định nghĩa locale `en_US` vào như hình:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<resource xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="http://ofbiz.apache.org/dtds/ofbiz-properties.xsd">
    <property key="OfbizDemoApplication">
        <value xml:lang="en">OfbizDemo Application</value>
        <value xml:lang="en_US">OfbizDemo Application</value>
        <value xml:lang="zh">OfbizDemo应用程庿</value>
        <value xml:lang="zh-TW">OfbizDemo應用程弿</value>
    </property>
    <property key="OfbizDemoCompanyName">
        <value xml:lang="en">OFBiz: OfbizDemo</value>
        <value xml:lang="en_US">OFBiz: OfbizDemo</value>
        <value xml:lang="zh-TW">OFBiz: OfbizDemo</value>
    </property>
</resource>
```


## Required works

 - [ ] List item
 - [ ]  
 - [ ]  
 - [ ] 

# 2 Export service using REST (nano project)

References:
 - https://cwiki.apache.org/confluence/display/OFBIZ/Export+service+using+REST

##  Extracting data from Ofbiz database

## Serving data via REST service
## Required works

 - [ ] List item
 - [ ]  
 - [ ]  
 - [ ] 

# 3 Beautify/organizing accounting page (micro project)

References:

## Authentication restriction (Encoding data)
## Required works

 - [ ] List item
 - [ ]  
 - [ ]  
 - [ ] 


# 4 A milli project

## Opening an application on local network

## Mobile support

## Required works

 - [ ] List item
 - [ ]  
 - [ ]  
 - [ ] 

# 5 A centi project 


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2MzY5NDc3OCw4MDk0NjAxOTMsLTIwMD
U0MDM0NDBdfQ==
-->