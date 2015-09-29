# QuickSolnShareDrive
This is to share the links or files among the quick soln team

girish.damodar@gmail.com
http://books.zkoss.org/wiki/Setup_MySQL_DB_in_Eclipse


http://www.ozekisms.com/index.php?owpn=583 - send sms

https://developers.google.com/api-client-library/java/apis/mapsengine/v1 - to download the google api client library.

http://christianvarga.com/how-to-calculate-driving-distance-between-2-locations-with-google-maps-api/

http://mobile.dzone.com/sites/all/files/Source-Code-Java-SMS-Example-HTTP_0.zip - Send Sms 

http://jsfiddle.net/er4s3/1/

https://javamail.java.net/nonav/docs/api/com/sun/mail/smtp/SMTPTransport.html - Send sms through smtp
https://developers.google.com/eclipse/docs/getting_started - google plugin

http://www.drivingrouteplanner.com/

https://developers.google.com/maps-engine/documentation/hello-world - Google map

http://www.1stwebdesigner.com/distance-finder-google-maps-api/

http://4byte.cn/question/762535/google-map-with-dynamic-and-multiple-destinations.html


http://www.java2s.com/Code/Jar/g/Downloadgwtmaps3jar.htm

http://www.sitepoint.com/find-a-route-using-the-geolocation-and-the-google-maps-api/
https://developers.google.com/maps/documentation/directions/intro?csw=1
http://dev.mysql.com/doc/refman/5.6/en/mysql.html
https://dev.mysql.com/doc/refman/5.0/en/entering-queries.html

mysql-connector-java-5.1.23-bin.jar - connector


 
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

//import com.mysql.jdbc.Driver;

public class TestDistance {
	public static void main(String[] args) {
		Connection conn = null;
		Statement stmt = null;
		ResultSet rs = null;
		try {
//			new com.mysql.jdbc.Driver();
			Class.forName("com.mysql.jdbc.Driver").newInstance();
// conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/techtool?user=root&password=''");
			String connectionUrl = "jdbc:mysql://'scsbwin-465906'/techtool";
			String connectionUser = "root";
			String connectionPassword = "";
			conn = DriverManager.getConnection(connectionUrl, connectionUser, connectionPassword);
			stmt = conn.createStatement();
			rs = stmt.executeQuery("SELECT * FROM employees");
			while (rs.next()) {
				String id = rs.getString("id");
				String firstName = rs.getString("first_name");
				String lastName = rs.getString("last_name");
				System.out.println("ID: " + id + ", First Name: " + firstName
						+ ", Last Name: " + lastName);
			}
		} catch (Exception e) {
			e.printStackTrace();
		} finally {
			try { if (rs != null) rs.close(); } catch (SQLException e) { e.printStackTrace(); }
			try { if (stmt != null) stmt.close(); } catch (SQLException e) { e.printStackTrace(); }
			try { if (conn != null) conn.close(); } catch (SQLException e) { e.printStackTrace(); }
		}
	}
}
 
