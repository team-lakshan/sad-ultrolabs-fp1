# Instructions

### 1. Clone the repository first

### 2. Add the MySQL database class to your repository

#### Location: `src/util/MySQL.java`

```sh
package util;

/**
 * MySQL Database Utility Class
 * @author Nawwa
 */
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class MySQL {

    private static Connection connection;

    static {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/sadgp1", "root", "");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public static ResultSet execute(String query) throws Exception {
        Statement statement = connection.createStatement();
        if (query.startsWith("SELECT")) {
            return statement.executeQuery(query);
        } else {
            statement.executeUpdate(query);
            return null;
        }
    }
}
```

### 3. Make a copy of nbproject.sample and rename it to nbproject
### 4. Open the project using NetBeans IDE (Step 3 is required for this step to work)
### 5. Copy the Google Drive library collection to your local PC 
```sh 
https://drive.google.com/drive/folders/1O-sHmuYiOkjf923ZMJpEG81Ht-lbuwJ1?usp=sharing
```
### 6. Now, add the library files to the project 
