import java.sql.*;
import java.util.Scanner;

public class ProductManager {
    
    private static final String URL = "jdbc:mysql://localhost:3306/productdb";
    private static final String USER = "root";
    private static final String PASSWORD = "password"; // Change to your actual password
    
   
    private static Connection connection = null;
    private static Scanner scanner = new Scanner(System.in);
    
    public static void main(String[] args) {
        try {
           
            Class.forName("com.mysql.cj.jdbc.Driver");
            
           
            System.out.println("Connecting to database...");
            connection = DriverManager.getConnection(URL, USER, PASSWORD);
            
            
            connection.setAutoCommit(false);
            
            boolean exit = false;
            while (!exit) {
                printMenu();
                int choice = scanner.nextInt();
                scanner.nextLine(); 
                
                switch (choice) {
                    case 1:
                        createProduct();
                        break;
                    case 2:
                        readAllProducts();
                        break;
                    case 3:
                        updateProduct();
                        break;
                    case 4:
                        deleteProduct();
                        break;
                    case 5:
                        exit = true;
                        break;
                    default:
                        System.out.println("Invalid choice. Please try again.");
                }
            }
            
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            
            try {
                if (connection != null) connection.close();
                if (scanner != null) scanner.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
        }
        System.out.println("Program terminated.");
    }
    
    private static void printMenu() {
        System.out.println("\n===== Product Management System =====");
        System.out.println("1. Create New Product");
        System.out.println("2. View All Products");
        System.out.println("3. Update Existing Product");
        System.out.println("4. Delete Product");
        System.out.println("5. Exit");
        System.out.print("Enter your choice: ");
    }
    
    private static void createProduct() {
        PreparedStatement pstmt = null;
        
        try {
            System.out.println("\n--- Create New Product ---");
            System.out.print("Enter Product ID: ");
            int productId = scanner.nextInt();
            scanner.nextLine(); // Consume newline
            
            System.out.print("Enter Product Name: ");
            String productName = scanner.nextLine();
            
            System.out.print("Enter Price: ");
            double price = scanner.nextDouble();
            
            System.out.print("Enter Quantity: ");
            int quantity = scanner.nextInt();
            
            
            String sql = "INSERT INTO Product (ProductID, ProductName, Price, Quantity) VALUES (?, ?, ?, ?)";
            pstmt = connection.prepareStatement(sql);
            
            
            pstmt.setInt(1, productId);
            pstmt.setString(2, productName);
            pstmt.setDouble(3, price);
            pstmt.setInt(4, quantity);
            
            
            int rowsAffected = pstmt.executeUpdate();
            
            if (rowsAffected > 0) {
                
                connection.commit();
                System.out.println("Product created successfully!");
            } else {
                
                connection.rollback();
                System.out.println("Product creation failed.");
            }
            
        } catch (SQLException se) {
           
            try {
                if (connection != null) connection.rollback();
            } catch (SQLException rollbackEx) {
                rollbackEx.printStackTrace();
            }
            System.out.println("Error: " + se.getMessage());
        } finally {
            
            try {
                if (pstmt != null) pstmt.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
        }
    }
    
    private static void readAllProducts() {
        PreparedStatement pstmt = null;
        ResultSet rs = null;
        
        try {
            System.out.println("\n--- All Products ---");
            
            
            String sql = "SELECT * FROM Product";
            pstmt = connection.prepareStatement(sql);
            
           
            rs = pstmt.executeQuery();
            
            
            System.out.println("ProductID\tProductName\tPrice\tQuantity");
            System.out.println("--------------------------------------------------");
            
           
            boolean found = false;
            while (rs.next()) {
                found = true;
                int productId = rs.getInt("ProductID");
                String productName = rs.getString("ProductName");
                double price = rs.getDouble("Price");
                int quantity = rs.getInt("Quantity");
                
                System.out.printf("%d\t\t%-12s\t%.2f\t%d\n", productId, productName, price, quantity);
            }
            
            if (!found) {
                System.out.println("No products found in the database.");
            }
            
        } catch (SQLException se) {
            System.out.println("Error: " + se.getMessage());
        } finally {
           
            try {
                if (rs != null) rs.close();
                if (pstmt != null) pstmt.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
        }
    }
    
    private static void updateProduct() {
        PreparedStatement pstmt = null;
        ResultSet rs = null;
        
        try {
            System.out.println("\n--- Update Product ---");
            System.out.print("Enter Product ID to update: ");
            int productId = scanner.nextInt();
            scanner.nextLine(); 
            
           
            String checkSql = "SELECT * FROM Product WHERE ProductID = ?";
            pstmt = connection.prepareStatement(checkSql);
            pstmt.setInt(1, productId);
            rs = pstmt.executeQuery();
            
            if (rs.next()) {
                
                String currentName = rs.getString("ProductName");
                double currentPrice = rs.getDouble("Price");
                int currentQuantity = rs.getInt("Quantity");
                
                rs.close();
                pstmt.close();
                
               
                System.out.println("Current Product Name: " + currentName);
                System.out.print("Enter new Product Name (press Enter to keep current): ");
                String newName = scanner.nextLine();
                if (newName.isEmpty()) {
                    newName = currentName;
                }
                
                System.out.println("Current Price: " + currentPrice);
                System.out.print("Enter new Price (enter -1 to keep current): ");
                double newPrice = scanner.nextDouble();
                if (newPrice == -1) {
                    newPrice = currentPrice;
                }
                
                System.out.println("Current Quantity: " + currentQuantity);
                System.out.print("Enter new Quantity (enter -1 to keep current): ");
                int newQuantity = scanner.nextInt();
                if (newQuantity == -1) {
                    newQuantity = currentQuantity;
                }
                
                
                String updateSql = "UPDATE Product SET ProductName = ?, Price = ?, Quantity = ? WHERE ProductID = ?";
                pstmt = connection.prepareStatement(updateSql);
                pstmt.setString(1, newName);
                pstmt.setDouble(2, newPrice);
                pstmt.setInt(3, newQuantity);
                pstmt.setInt(4, productId);
                
                int rowsAffected = pstmt.executeUpdate();
                
                if (rowsAffected > 0) {
                   
                    connection.commit();
                    System.out.println("Product updated successfully!");
                } else {
                   
                    connection.rollback();
                    System.out.println("Product update failed.");
                }
                
            } else {
                System.out.println("Product with ID " + productId + " not found.");
            }
            
        } catch (SQLException se) {
            
            try {
                if (connection != null) connection.rollback();
            } catch (SQLException rollbackEx) {
                rollbackEx.printStackTrace();
            }
            System.out.println("Error: " + se.getMessage());
        } finally {
            
            try {
                if (rs != null) rs.close();
                if (pstmt != null) pstmt.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
        }
    }
    
    private static void deleteProduct() {
        PreparedStatement pstmt = null;
        ResultSet rs = null;
        
        try {
            System.out.println("\n--- Delete Product ---");
            System.out.print("Enter Product ID to delete: ");
            int productId = scanner.nextInt();
            
            
            String checkSql = "SELECT ProductName FROM Product WHERE ProductID = ?";
            pstmt = connection.prepareStatement(checkSql);
            pstmt.setInt(1, productId);
            rs = pstmt.executeQuery();
            
            if (rs.next()) {
                String productName = rs.getString("ProductName");
                rs.close();
                pstmt.close();
                
                System.out.println("Are you sure you want to delete product: " + productName + " (ID: " + productId + ")? (y/n)");
                scanner.nextLine(); 
                String confirmation = scanner.nextLine();
                
                if (confirmation.equalsIgnoreCase("y")) {
                   
                    String deleteSql = "DELETE FROM Product WHERE ProductID = ?";
                    pstmt = connection.prepareStatement(deleteSql);
                    pstmt.setInt(1, productId);
                    
                    int rowsAffected = pstmt.executeUpdate();
                    
                    if (rowsAffected > 0) {
                       
                        connection.commit();
                        System.out.println("Product deleted successfully!");
                    } else {
                       
                        connection.rollback();
                        System.out.println("Product deletion failed.");
                    }
                } else {
                    System.out.println("Delete operation cancelled.");
                }
                
            } else {
                System.out.println("Product with ID " + productId + " not found.");
            }
            
        } catch (SQLException se) {
            
            try {
                if (connection != null) connection.rollback();
            } catch (SQLException rollbackEx) {
                rollbackEx.printStackTrace();
            }
            System.out.println("Error: " + se.getMessage());
        } finally {
            
            try {
                if (rs != null) rs.close();
                if (pstmt != null) pstmt.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
        }
    }
}
