import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
public class DatabaseDeleteExample 
{
private static final String JDBC_URL = "jdbc:mysql://localhost:3306/mydatabase";
private static final String USERNAME = "root";
private static final String PASSWORD = "password";
public static void main(String[] args) 
{
try (Connection connection = DriverManager.getConnection(JDBC_URL, USERNAME, PASSWORD)) 
{
String deleteQuery = "DELETE FROM users WHERE id = ?";
try (PreparedStatement deleteStmt = connection.prepareStatement(deleteQuery)) 
{
deleteStmt.setInt(1, 2); 
int rowsAffected = deleteStmt.executeUpdate();
if (rowsAffected > 0) {
System.out.println("Row deleted successfully.");
                }
else
System.out.println("No rows were deleted.");
                }
            } catch (SQLException e) {
e.printStackTrace();
            }
        } 
catch (SQLException e) {
e.printStackTrace();
        }
    }
}