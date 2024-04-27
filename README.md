# ip-9
// package
package pack;
 class book 
{
  public String name;
  public String author;
   public int IBSN;
    public double price;
   
public book(String name,String author,int IBSN,double price)
{
this.name=name;
this.author=author; 
this.IBSN=IBSN;
this.price=price;
}
public String getname()
{
    return name;
}
public String getauthor()
{
    return author;
}
public int getIBSN()
{
    return IBSN;
}
public double getprice()
{
    return price;
}
public String tostring()
{
    return "title"+name + "author" +author+ "IBSN" +IBSN + "price" +price;
}
 public void setname(String name)
{
   this.name=name; 
}

 public void setauthor(String author)
{
   this.author=author; 
   }
  public void setIBSN(int IBSN)
{
   this.IBSN=IBSN; 
}
    public void setprice(double price)
{
   this.price=price; 
}
}
//java file
package pack;
import java.util.*;
public class Book 
{
    public static void main(String[] args)
    {
        ArrayList <Book>  bk = new ArrayList<>();
        bk.add(new Book("book1","JohnDoe",123456,10.99));
        bk.add(new Book("book2","JaneSmith",987654,05.99));
        bk.add(new Book("book3","Bob Johnson",135790,20.50));
        collections.sort(bk,new sortbyprice());
        System.out.println(bk);
        class sortbyprice implements comparator<Book>
        {
            public int compare(book b1,book b2)
            {
                return (int) (b1.price - b2.price);
            }
        }
    }

    public Book(String book1, String johnDoe, int i, double d) {
        throw new UnsupportedOperationException("Not supported yet."); //To change body of generated methods, choose Tools | Templates.
    }
}
//jsp file
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<%@page import="pack.sortbyprice"%>
<%@page contentType="text/html" pageEncoding="UTF-8"%>
<%@page import="java.util.*"%>
<%@page import="pack.Book"%>
<body>
<%
    ArrayList<Book> bk = new ArrayList<>();
    bk.add(new Book("book1", "JohnDoe", 123456, 10.99));
    bk.add(new Book("book2", "JaneSmith", 987654, 5.99));
    bk.add(new Book("book3", "Bob Johnson", 135790, 20.50));

   Collections.sort(bk, new Comparator<Book>() {
    public int compare(Book b1, Book b2) {
        return (int) (b1.price - b2.price);
    }
});


    pageContext.setAttribute("boo", bk);
%>

   <c:forEach var="boo" items="$(PageScope.boo)">
        <c:out value="$(boo.name)"/>
    </c:forEach>
    <c:forEach var="boo" items="$(PageScope.boo)">
        <c:out value="$(boo.author)"/>
    </c:forEach>
   <c:forEach var="boo" items="$(PageScope.boo)">
        <c:out value="$(boo.IBSN)"/>
    </c:forEach>
   <c:forEach var="boo" items="$(PageScope.boo)">
        <c:out value="$(boo.price)"/>
    </c:forEach>
    </body>
