# Automation-project-Selenium-
Amazon automation project
import java.util.ArrayList;
import java.util.Iterator;
import java.util.Set;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;

public class Amazon_project {

	public static void main(String[] args) throws InterruptedException
	{
		System.setProperty("webdriver.gecko.driver","C:\\Users\\rbi\\Desktop\\Selenium jar\\mozila\\geckodriver.exe");
		WebDriver w = new FirefoxDriver();
		// To Open Url
		w.get("http://amazon.in");
		
		//To check Title Of Current page
		System.out.println(w.getCurrentUrl());

		//DASHBOARD MENU_BAR
				//w.findElement(By.xpath("//*[@id=\"nav-hamburger-menu\"]/span")).click();
				//Thread.sleep(2000);)
				
				w.findElement(By.xpath("//*[@id=\"nav-xshop\"]/a[1]")).click();
				Thread.sleep(2000);
		    	
		        w.findElement(By.xpath("//*[@id=\"nav-xshop\"]/a[2]")).click();
		        Thread.sleep(2000);
		    	
		        w.findElement(By.xpath("//*[@id=\"nav-xshop\"]/a[3]")).click();
		        Thread.sleep(2000);
		    	
		        w.findElement(By.xpath("//*[@id=\"nav-xshop\"]/a[4]")).click();
		        Thread.sleep(2000);
		    	
		        w.findElement(By.xpath("//*[@id=\"nav-xshop\"]/a[5]")).click();
		        Thread.sleep(2000);
		        
		        w.findElement(By.xpath("/html/body/div[1]/header/div/div[4]/div[2]/div[2]/div/a[6]")).click();
		    	
		        w.findElement(By.xpath("//*[@id=\"nav-link-prime\"]/span[1]")).click();
		        Thread.sleep(2000);
		        
		        
		        w.findElement(By.xpath("//*[@id=\"nav-xshop\"]/a[8]")).click();
		        Thread.sleep(2000);
		        
		        w.findElement(By.xpath("//*[@id=\"nav-xshop\"]/a[9]")).click();
		        
		        w.findElement(By.xpath("/html/body/div[1]/header/div/div[1]/div[3]/div/a[1]/span/span[2]/span[1]")).click();
		        System.out.println("Done Dashbord menubar");
		    	
		   
		// CREATE ACCOUNT WITH ALREADY REGISERD ACCOUNT.... ..Negative test case
	/*	w.findElement(By.xpath("//*[@id=\"nav-link-accountList\"]/span")).click();
		        w.findElement(By.xpath("//*[@id=\"createAccountSubmit\"]")).click();
		        w.findElement(By.id("ap_customer_name")).sendKeys("Namrata");
		        w.findElement(By.id("ap_phone_number")).sendKeys("8169566159");
		        w.findElement(By.id("ap_email")).sendKeys("numshinde@gmail.com");
		        w.findElement(By.id("ap_password")).sendKeys("India@123");
		        w.findElement(By.id("continue")).click();
		        Thread.sleep(2000);	
		        //(Throwing error message)
		    
		    	//click on sign in on same page.
		        w.findElement(By.xpath("/html/body/div[1]/div[1]/div[2]/div/div[2]/div/form/div/div/div[8]/a")).click();

		//SIGN IN with forget password
		/*w.findElement(By.xpath("//*[@id=\"nav-link-accountList\"]/span")).click();
		w.findElement(By.id("ap_email")).sendKeys("numshinde@gmail.com");
		w.findElement(By.id("continue")).click();
		w.findElement(By.linkText("Forgot Password")).click();
		w.findElement(By.id("continue")).click();
		w.findElement(By.id("cvf-input-code")).sendKeys("581234");
		w.findElement(By.className("a-button-input")).click();
		w.findElement(By.id("ap_fpp_password")).sendKeys("Namrata@123");
		w.findElement(By.id("ap_fpp_password_check")).sendKeys("Namrata@123");
		w.findElement(By.id("continue")).click();	*/

		//SIGN IN with valid username And password
		w.findElement(By.xpath("//*[@id=\"nav-link-accountList\"]/span")).click();	
		w.findElement(By.id("ap_email")).sendKeys("numshinde@gmail.com");
		w.findElement(By.id("continue")).click();
		w.findElement(By.id("ap_password")).sendKeys("Namrata@123");
		w.findElement(By.id("signInSubmit")).click();
		System.out.println("Done Sign in with valid data");

		//search product
		w.findElement(By.id("twotabsearchtextbox")).sendKeys("Fastrack watches for women");
		w.findElement(By.id("nav-search-submit-button")).click();
		JavascriptExecutor js = (JavascriptExecutor) w;
		js.executeScript("window.scrollBy(0,1500)","");		
		
		
		w.findElement(By.xpath("/html/body/div[1]/div[2]/div[1]/div/div[1]/div/span[3]/div[2]/div[1]/div/span/div/div/div/div/div[2]/div/span/a/div/img")).click();
		Thread.sleep(2000);
	// WINDOW HANDLING 
		Set<String> windows = w.getWindowHandles();
		Iterator<String> it=  windows.iterator();
		String parentwindow = it.next();
		String childwindow = it.next();
		w.switchTo().window(childwindow);
		
		//OR
		
		
		//ArrayList<String> tabs2 = new ArrayList<String> (w.getWindowHandles());
	 //   w.switchTo().window(tabs2.get(1));
	  //  w.switchTo().window(tabs2.get(0));
	   Thread.sleep(5000);
		
	    // ADD TO CART PRODUCT
	  Select quantity = new Select (w.findElement(By.id("quantity")));
      quantity.selectByValue("2");

	 w.findElement(By.id("add-to-cart-button")).click();
	 w.findElement(By.id("nav-cart-count")).click();
	 System.out.println("Add to cart is done");
	 Thread.sleep(5000);	
	
	   // Delete from Add To Cart
	 w.findElement(By.name("submit.delete.C7283f235-1e8d-430d-85df-64456e819772")).click();
	 System.out.println("Done with Delete");
	 Thread.sleep(3000);	
    
		        
	     // mouse hover 
		 	   Actions action = new Actions(w);
		        WebElement element= w.findElement(By.xpath("//*[@id=\"nav-link-accountList\"]/span/span"));
		        action.moveToElement(element).perform();
		        Thread.sleep(3000);	
		     
		   // SIGN OUT
		         w.findElement(By.xpath("/html/body/div[1]/div[1]/header/div/div[3]/div[2]/div[2]/div/div[2]/a[13]/span")).click();
		        System.out.println("Done with sigh out");	
	
		
		
		
		
	}
		
	}
