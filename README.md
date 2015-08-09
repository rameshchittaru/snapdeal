# snapdeal
loin to snapdeal 


package keyboardevent;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Action;
import org.openqa.selenium.interactions.Actions;

public class snapdeal{
	

	public static void main(String[] args) {
		
		WebDriver driver = new FirefoxDriver();
		
		driver.manage().window().maximize();
		driver.get("http://www.snapdeal.com/");
		
		WebElement ele = driver.findElement(By.xpath(".//*[@id='leftNavNemu']/div/div[1]/ul/li[3]/a/span[1]"));
		WebElement ele1 = driver.findElement(By.xpath(".//*[@id='leftNavNemu']/div/div[1]/ul/li[3]/div/ul/li[3]/a/span[1]"));
		WebElement ele2 = driver.findElement(By.xpath(".//*[@id='leftNavNemu']/div/div[1]/ul/li[3]/div/ul/li[3]/div/div/ul/li/div[1]/div/form/div[1]/p[6]/a"));
		
		
		Actions act = new Actions(driver);
		Action act1 = act.moveToElement(ele)
						.sendKeys(Keys.ARROW_DOWN)
						.moveToElement(ele1)
						.sendKeys(Keys.ARROW_DOWN)
						.moveToElement(ele2).click()
						.build();
		act1.perform();
		
		for(String handle: driver.getWindowHandles())
		{
			driver.switchTo().window(handle);
		}
		WebElement ele3 = driver.findElement(By.xpath(".//*[@id='slider-Price-id']/a[1]"));
		
		Actions act2 = new Actions(driver);
		Action act3 = act2.dragAndDropBy(ele3, 8, 0).build();
		act3.perform();
		
		
	}
}

