# pru
rom selenium.webdriver.common.keys import Keys

# Launch the web browser (e.g., Chrome)
driver = webdriver.Chrome()

# Open a website
driver.get("https://www.example.com")

# Perform automated actions
search_box = driver.find_element_by_name("q")
search_box.send_keys("Automation")
search_box.send_keys(Keys.RETURN)

# Extract information from the webpage
results = driver.find_elements_by_css_selector(".search-results .result")
for result in results:
    title = result.find_element_by_css_selector(".title").text
    url = result.find_element_by_css_selector(".url").text
    print("Title:", title)
    print("URL:", url)
    print()

# Close the web browser
driver.quit()
