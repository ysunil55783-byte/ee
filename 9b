import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
public class DatabaseInsertExample 
{
private static final String JDBC_URL = "jdbc:mysql://localhost:3306/mydatabase";
private static final String USERNAME = "root";
private static final String PASSWORD = "password";
public static void main(String[] args) {
try (Connection connection = DriverManager.getConnection(JDBC_URL, USERNAME, PASSWORD)) 
{
String createTableQuery = "CREATE TABLE IF NOT EXISTS users (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255), email VARCHAR(255))";
try (PreparedStatement createTableStmt = connection.prepareStatement(createTableQuery)) 
{
createTableStmt.execute();
            }
            String insertQuery = "INSERT INTO users (name, email) VALUES (?, ?)";
try (PreparedStatement insertStmt = connection.prepareStatement(insertQuery)) 
{
insertStmt.setString(1, "John Doe");
insertStmt.setString(2, "johndoe@example.com");
insertStmt.executeUpdate();
insertStmt.setString(1, "Jane Doe");
insertStmt.setString(2, "janedoe@example.com");
insertStmt.executeUpdate();
System.out.println("Data inserted successfully.");
            }
        }
catch (SQLException e) {
e.printStackTrace();
        }
    }
}