# Login

 System.setProperty("webdriver.chrome.driver","resources/chromedriver.exe");
        WebDriver driver = new ChromeDriver();
        driver.get("https://www.saucedemo.com/");
        //Scenario 1
        WebElement username = driver.findElement(By.xpath("//input[@placeholder= 'Username']"));
        username.sendKeys("");
        WebElement password = driver.findElement(By.xpath("//input[@placeholder= 'Password']"));
        password.sendKeys("123");
        WebElement login = driver.findElement(By.cssSelector("input[type= 'submit']"));
        login.click();
        WebElement errorMessage = driver.findElement(By.cssSelector("div[class = \"error-message-container error\"]"));
        String msg = errorMessage.getText();
        System.out.println(msg);
        Assert.assertEquals(errorMessage.getText(),"Epic sadface: Username is required");

        //Scenario 2
        WebElement username = driver.findElement(By.xpath("//input[@placeholder= 'Username']"));
        username.sendKeys("Musa");
        WebElement password = driver.findElement(By.xpath("//input[@placeholder= 'Password']"));
        password.sendKeys("");
        WebElement login = driver.findElement(By.cssSelector("input[type= 'submit']"));
        login.click();
        WebElement errorMessage = driver.findElement(By.cssSelector("div[class = \"error-message-container error\"]"));
        String msg = errorMessage.getText();
        System.out.println(msg);
        Assert.assertEquals(errorMessage.getText(),"Epic sadface: Password is required");

        //Scenario 3
        WebElement username = driver.findElement(By.xpath("//input[@placeholder= 'Username']"));
        username.sendKeys("Musa");
        WebElement password = driver.findElement(By.xpath("//input[@placeholder= 'Password']"));
        password.sendKeys("123");
        WebElement login = driver.findElement(By.cssSelector("input[type= 'submit']"));
        login.click();
        WebElement errorMessage = driver.findElement(By.cssSelector("div[class = \"error-message-container error\"]"));
        String msg = errorMessage.getText();
        System.out.println(msg);
        Assert.assertEquals(errorMessage.getText(),"Epic sadface: Username and password do not match any user in this service");


        //Scenario 4
        WebElement username = driver.findElement(By.xpath("//input[@placeholder= 'Username']"));
        username.sendKeys("");
        WebElement password = driver.findElement(By.xpath("//input[@placeholder= 'Password']"));
        password.sendKeys("");
        WebElement login = driver.findElement(By.cssSelector("input[type= 'submit']"));
        login.click();
        WebElement errorMessage = driver.findElement(By.cssSelector("div[class = \"error-message-container error\"]"));
        String msg = errorMessage.getText();
        System.out.println(msg);
        Assert.assertEquals(errorMessage.getText(),"Epic sadface: Username is required");



        //Scenario 5
        WebElement username = driver.findElement(By.xpath("//input[@placeholder= 'Username']"));
        username.sendKeys("standard_user");
        WebElement password = driver.findElement(By.xpath("//input[@placeholder= 'Password']"));
        password.sendKeys("secret_sauce");
        WebElement login = driver.findElement(By.cssSelector("input[type= 'submit']"));
        login.click();
        WebElement products = driver.findElement(By.xpath("//span[@class = \"title\"]"));
        Assert.assertTrue(products.isDisplayed());

