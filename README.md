# Project

package configc;

import java.io.File;
import java.io.IOException;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.io.FileHandler;


import configc.Testbase;

public class Capture {

		
		static WebDriver dr;

		public static void main(String[] args) throws InterruptedException, IOException 
		
		{
			
			dr= Testbase.init();
			dr.get("https://www.toolsqa.com/");
			
			JavascriptExecutor je=(JavascriptExecutor) dr;
			
			je.executeScript("window.scrollBy(0,800)","");
			
			je.executeScript("window.scrollBy(0,800)","");
			Thread.sleep(500); 
			
			je.executeScript("window.scrollBy(0,-800)","");
			
			je.executeScript("window.scrollBy(0,-800)","");
			
			
			WebElement e = dr.findElement(By.xpath("//a[text()='Appium']"));
			
			je.executeScript("arguments[0].scrollIntoView(false);" , e);
			je.executeScript("window.scrollBy(0,300)","");
			je.executeScript("arguments[0].click();" , e);
		// TODO Auto-generated constructor stub
			
			File f=((TakesScreenshot)dr).getScreenshotAs(OutputType.FILE);
			
			FileHandler.copy(f,new File ("Test"+".jpg"));
	}

		

}
