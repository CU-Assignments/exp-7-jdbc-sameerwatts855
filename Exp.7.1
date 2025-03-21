import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class EmployeeDataFetcher {
    public static void main(String[] args) {
        
        String url = "jdbc:mysql://localhost:3306/employeedb";
        String user = "root";
        String password = "password"; 
        
        
        String query = "SELECT EmpID, Name, Salary FROM Employee";
        
       
        Connection connection = null;
        Statement statement = null;
        ResultSet resultSet = null;
        
        try {

            Class.forName("com.mysql.cj.jdbc.Driver");
            
           
            System.out.println("Connecting to database...");
            connection = DriverManager.getConnection(url, user, password);
            
           
            System.out.println("Creating statement...");
            statement = connection.createStatement();
            resultSet = statement.executeQuery(query);
            
           
            System.out.println("\nEmployee Records:");
            System.out.println("------------------------------------------");
            System.out.println("EmpID\tName\t\tSalary");
            System.out.println("------------------------------------------");
            
           
            while (resultSet.next()) {
                int empId = resultSet.getInt("EmpID");
                String name = resultSet.getString("Name");
                double salary = resultSet.getDouble("Salary");
                
                
                System.out.printf("%d\t%-10s\t%.2f\n", empId, name, salary);
            }
            
        } catch (SQLException se) {
           
            se.printStackTrace();
        } catch (Exception e) {
            
            e.printStackTrace();
        } finally {
            
            try {
                if (resultSet != null) resultSet.close();
                if (statement != null) statement.close();
                if (connection != null) connection.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
        }
        System.out.println("\nProgram completed.");
    }
}
