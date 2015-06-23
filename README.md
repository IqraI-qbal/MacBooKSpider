# MacBooKSpider
package TestNG;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;

public class MacBook {

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		WebDriver WD=new FirefoxDriver();
		 // Wait for page  load
		WD.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		// And now use this to visit shophive.com/apple/mac
		WD.navigate().to("http://www.shophive.com/apple/mac?p=1");
		// Alternatively the same thing can be done like this
		//driver.get("http://www.comshophive.com/apple/mac");
		WD.navigate().forward();
		WD.navigate().back();

		WD.manage().window().maximize();

		java.util.List<WebElement>
		 // Find the text input element by its classname
		price = WD.findElements(By.className("price-box")); 
		java.util.List<WebElement>
		pName = WD.findElements(By.className("product-name"));
		try{
		for(int c=0;c<=price.size();c++)
		{
		System.out.println("ProductNO: "+c+1+ "\n Product name = " + pName.get(c).getText() + "\nPrice = "+price.get(c).getText() ); 
		}

		}catch(IndexOutOfBoundsException e)
		{
		System.out.println("End");
		}

		WD.close();
	}

}
