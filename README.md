Step 1: Create a new Web Application Project

    Open NetBeans.
    Go to File -> New Project.
    Choose Java Web category and select Web Application.
    Click Next and follow the wizard to create the project.

Step 2: Create a Java Web Service

    Right-click on the Source Packages folder in your project.
    Select New -> Java Class.
    Name the class WebService1 and click Finish.
    Implement the method rtoD to convert Rupees to Dollars in this class.

java code netbeans

package tycs;

public class WebService1 {
    public double rtoD(double rupees) {
        return rupees / 73.85; // Assuming 1 USD = 73.85 INR
    }
}

Step 3: Create JSP Pages

    Right-click on the Web Pages folder in your project.
    Select New -> JSP.
    Name the JSP page index.jsp and click Finish.
    Replace the content of index.jsp with the HTML form code provided in your question.

jsp index.jsp code

<%@page contentType="text/html" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
    <head>
        <title>--Calculation--</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    </head>
    <body>
        <form action="result.jsp" method="POST"> 
            Enter Rupees:<input type="text" name="txt1" value="" /> <br>
            <input type="submit" value="Convert to Dollar"/> <br>
        </form>
    </body>
</html>

    Right-click on the Web Pages folder again.
    Select New -> JSP.
    Name the JSP page result.jsp and click Finish.
    Replace the content of result.jsp with the Java code provided in your question.

jsp newhtml.html code

<%@page contentType="text/html" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <title>JSP Page</title>
    </head>
    <body>
        <h1>Hello World...lets convert dollar to rupess!</h1>
       <%
            tycs.WebService1 obj = new tycs.WebService1();
            tycs.WebService1Soap port = obj.getWebService1Soap();
            double num1 = Double.parseDouble(request.getParameter("txt1"));
            double result = port.rtoD(num1);
            out.println("Conversion from Rs to Dollar is " + result);
       %>
    </body>
</html>

Step 4: Run the Project

