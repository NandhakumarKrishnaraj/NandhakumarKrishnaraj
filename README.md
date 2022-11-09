package com.testNG.basic;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class WithoutDataProvider {

	@Test
	public void login() throws InterruptedException {

		System.setProperty("webdriver.chrome.driver", "C:\\Users\\Kannathasan.E\\Downloads\\chromedriver_win32 (2)\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();

		driver.manage().timeouts().implicitlyWait(20, TimeUnit.SECONDS);
		driver.get("https://letcode.in/");
		driver.findElement(By.linkText("Log in")).click();
		driver.findElement(By.name("email")).sendKeys("koushik350@gmail.com");
		driver.findElement(By.name("password")).sendKeys("Pass123$");
		Thread.sleep(2000);
		driver.findElement(By.xpath("//button[.='LOGIN']")).click(); 
		System.out.println("Logged in successfully");
		String title = driver.getTitle();
		System.out.println("Title is "+title); 
		driver.quit();

	}
	
}

