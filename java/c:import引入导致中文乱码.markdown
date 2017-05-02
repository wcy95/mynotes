# c:import引入导致中文乱码  
先检查，页面头部是否加入：

><%@   page   language="Java"   contentType="text/html;   charset=utf-8"%>

 

然后检查，c:import中是否加入了编码格式支持：

><c:import   url="http://localhost:80/templates/a.jsp"   charEncoding="UTF-8" />  

或者：
使用c:import标签中的c:param传递中文时，可能会参数乱码
解决措施：在使用参数的jsp前面加fmt:requestEncoding

    <fmt:requestEncoding value="utf8" />
    <h1>${param.msg}</h1>

