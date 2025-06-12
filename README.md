
package dboperation;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class DDBconnectionexample {
	public static void main(String[] args) throws ClassNotFoundException, SQLException {
		Class.forName("com.mysql.cj.jdbc.Driver");
		Connection connection = DriverManager.getConnection("jdbc:mysql://root@localhost/example_selenium");
		Statement statement = connection.createStatement();
		ResultSet result = statement.executeQuery("SELECT * FROM `new`");
		while (result.next()) {
			System.out.println("name : " + result.getString(1) + "  -  nic name : " + result.getString(2));
		}
	}

