## 1. JUnit

- Difference between each annotation in `JUnit 4 & 5`

<pre class="lang-java s-code-block"><code data-highlighted="yes" class="hljs language-java">+-------------------------------------------------------------------------------------------------------+
¦                                       Feature                            ¦   Junit <span class="hljs-number">4</span>    ¦   Junit <span class="hljs-number">5</span>   ¦
¦--------------------------------------------------------------------------+--------------+-------------¦
¦ Execute before all test methods of the <span class="hljs-keyword">class</span> <span class="hljs-title class_">are</span> executed.               ¦ <span class="hljs-meta">@BeforeClass</span> ¦ <span class="hljs-meta">@BeforeAll</span>  ¦
¦ Used with <span class="hljs-keyword">static</span> method.                                                 ¦              ¦             ¦
¦ For example, This method could contain some initialization code          ¦              ¦             ¦
¦-------------------------------------------------------------------------------------------------------¦
¦ Execute after all test methods in the current class.                     ¦ <span class="hljs-meta">@AfterClass</span>  ¦ <span class="hljs-meta">@AfterAll</span>   ¦
¦ Used with <span class="hljs-keyword">static</span> method.                                                 ¦              ¦             ¦
¦ For example, This method could contain some cleanup code.                ¦              ¦             ¦
¦-------------------------------------------------------------------------------------------------------¦
¦ Execute before each test method.                                         ¦ <span class="hljs-meta">@Before</span>      ¦ <span class="hljs-meta">@BeforeEach</span> ¦
¦ Used with non-<span class="hljs-keyword">static</span> method.                                             ¦              ¦             ¦
¦ For example, to reinitialize some <span class="hljs-keyword">class</span> <span class="hljs-title class_">attributes</span> used by the methods.  ¦              ¦             ¦
¦-------------------------------------------------------------------------------------------------------¦
¦ Execute after each test method.                                          ¦ <span class="hljs-meta">@After</span>       ¦ <span class="hljs-meta">@AfterEach</span>  ¦
¦ Used with non-<span class="hljs-keyword">static</span> method.                                             ¦              ¦             ¦
¦ For example, to roll back database modifications.                        ¦              ¦             ¦
+-------------------------------------------------------------------------------------------------------+
</code></pre>

- Reference: [Difference between `@Before`, `@BeforeClass`, `@BeforeEach` and `@BeforeAll`](https://www.youtube.com/watch?v=3qo7nvjQ2Wg&feature=youtu.be)

- Order of Execution: Dashed box -> optional annotation

<img src="https://i.sstatic.net/HKspz.png" alt="enter image description here">

- Example:

`SampleClass`:

```java
public class SampleClass {
    public String initializeData(){
        return "Initialize";
    }

    public String processDate(){
        return "Process";
    }
 }
```

`SampleTest`:

```java

public class SampleTest {

    private SampleClass sampleClass;

    @BeforeClass
    public static void beforeClassFunction(){
        System.out.println("Before Class");
    }

    @Before
    public void beforeFunction(){
        sampleClass=new SampleClass();
        System.out.println("Before Function");
    }

    @After
    public void afterFunction(){
        System.out.println("After Function");
    }

    @AfterClass
    public static void afterClassFunction(){
        System.out.println("After Class");
    }

    @Test
    public void initializeTest(){
        Assert.assertEquals("Initailization check", "Initialize", sampleClass.initializeData() );
    }

    @Test
    public void processTest(){
        Assert.assertEquals("Process check", "Process", sampleClass.processDate() );
    }

}

```

`Output`:

```
Before Class
Before Function
After Function
Before Function
After Function
After Class
```

## 2. How to Install Maven on Mac OS

- Reference: [install-maven-mac-os](https://www.digitalocean.com/community/tutorials/install-maven-mac-os)
