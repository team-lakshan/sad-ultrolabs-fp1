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
### 3 make a copy of nbproject.sample and rename it to nbproject
