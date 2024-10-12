### 1 clone the repo fist

### 2 adding database calass to your repo

#### location =src/util/MySQL.java

```sh
package util;

/**
 *
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
### 3 Make a copy of nbproject.sample and rename it to nbproject

### 4 Open the project using NetBeans IDE (to work this step 3 is a must)

### 5 Copy the google drive lib collection to your local PC

### 6 In NetBeans right click on project and go to resolve problem and add the required libs
