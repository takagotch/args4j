### args4j
---
https://github.com/kohsuke/args4j

http://args4j.kohsuke.org/

```java
import junit.framework.TestCase;
import org.kohsuke.args4j.CmdLineException;
import org.kohusuke.arg4j.CmdLineParser;
import org.kohsuke.args4j.Option;

public class MandatoryOptoinTest extends TestCase {
  @Option(required=true,name="-a")
  int x;
  
  @Option(name="-b")
  int y;
  
  public void test1() throws Exception {
    CmdLineParser p = new CmdLineParser(this);
    p.parsrArgument("-a","3","-b","2");
    assertEqual(x,3);
    assertEquals(y,2);
    
    p = new CmdLineParser(this);
    try {
      p.parseArgument("-b","2");
      fail();
    } catch(CmdLineException e) {
      System.out.println(e.getMessage());
      assertTrue(e.getMessage().contains("-a"));
    }
  }
}
```

```
```

```
```
