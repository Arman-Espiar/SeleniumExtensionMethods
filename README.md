# SeleniumExtensionMethods

Some practical Extension methods for Selenium Library.

## Usage

```csharp
using OpenQA.Selenium;
using OpenQA.Selenium.Firefox;

using SeleniumExtensionMethods.SeleniumExtensions.WebDriverExtensions;
using SeleniumExtensionMethods.SeleniumExtensions.WebElementExtensions;

IWebDriver driver = new FirefoxDriver();

string webUrl = "https://www.wikipedia.org/";

driver.WaitingForEachPageToLoad(TimeSpan.FromSeconds(3));
driver.GotoUrl(webUrl);
driver?.FindElementIfExistsByTagName("html")
	?.SendKeys(Keys.End);//scroll down
driver?.FindElementIfExistsById("searchLanguage")
	.ClickOnElement();
driver?.FindElementIfExistsByCssSelector("#searchLanguage > option:nth-child(21)")
	.ClickOnElement();
driver?.FindElementIfExists(By.Id("searchInput"))//This extension method and FindElementsIfExists are only for use in other extension methods, and you must use FindElementIfExistsById or FindElementsIfExistsById
	?.WriteInElement("کوروش");
driver?.FindElementIfExistsById("searchInput")
	?.WriteAppendInElement($" بزرگ");
driver?.FindElementIfExistsById("searchInput")
	?.WritePrependInElement("پادشاه " + Keys.Enter);
driver?.FindElementIfExistsByLinkText("کوروش بزرگ")
	?.ClickOnElement();
driver?.FindElementIfExistsById("p-lang-btn")
	.ClickOnElement();
driver?.FindElementIfExistsByXPath("/html/body/div[1]/div[2]/div[1]/div/ul[2]/li[3]/a")
	?.ClickOnElement();
driver?.FindElementIfExistsByCssSelector("#mw-normal-catlinks > ul:nth-child(2) > li:nth-child(1) > a:nth-child(1)")
	?.ClickOnElement();
driver?.FindElementIfExistsById("searchInput")
	?.WriteInElement("ljklkjfdfdjkfasdfl")
	?.ClearTextInputElement();
driver?.FindElementIfExistsByTagName("html")
	?.SendKeys(Keys.Home);//scroll up
driver?.FindElementIfExistsById("searchInput")
	?.SendKeys("Order of Assassins" + Keys.Enter);
driver?.FindElementIfExistsByXPath("/html/body/div[3]/div[3]/div[5]/div[1]/div[4]/ul/li[5]/a")
	?.ClickOnElement();
driver?.FindElementIfExistsById("p-logo")
	?.ClickOnElement();
driver?.FindElementIfExistsById("ca-viewsource")
	?.ClickOnElement();
driver?.FindElementIfExistsById("wpTextbox1")
	?.SendKeys(Keys.End);
  ```
  
  ## Note:
  
   extension methods instead of throw exception returned null.
   
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.
