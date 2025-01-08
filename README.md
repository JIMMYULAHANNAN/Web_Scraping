# Web_Scraping

### Explanation of the Code

This code demonstrates web scraping techniques using Python's `requests` and `BeautifulSoup` libraries to extract data from two websites: **Quotes to Scrape** and **Books to Scrape**. Here's a detailed explanation of each task:

---

### **TASK 1**: Get all authors from the first page of "Quotes to Scrape."

- **Steps**:
  1. `requests.get` fetches the HTML content of the page.
  2. `BeautifulSoup` parses the HTML using the `lxml` parser.
  3. `soup.select('.author')` locates all elements with the class `author` (used for author names).
  4. A loop iterates over these elements, and each name is added to a `set` to ensure uniqueness.

- **Purpose**: Extract unique author names listed on the first page.

---

### **TASK 2**: Create a list of all quotes on the first page.

- **Steps**:
  1. `soup.select('.text')` locates all elements containing quotes (with class `text`).
  2. A loop iterates over these elements, appending each quote's text to a `list`.

- **Purpose**: Gather all quotes displayed on the first page.

---

### **TASK 3**: Extract the top 10 tags from the home page.

- **Steps**:
  1. `soup.select('.tag-item')` identifies elements corresponding to top tags (class `tag-item`).
  2. A loop extracts and prints the text content of each tag.

- **Purpose**: Extract popular tags (like "Love," "Inspirational," etc.) listed on the home page.

---

### **TASK 4**: Loop through all pages to get unique authors.

- **Approach 1**: 
  1. Use a for loop to construct URLs for multiple pages (`http://quotes.toscrape.com/page/2/`).
  2. Parse each page and extract author names.
  3. Stop manually after a set number of pages (e.g., 10).

- **Approach 2**:
  1. Use a `while` loop to dynamically scrape until the last page.
  2. Check for the "No quotes found" message to stop the loop.
  3. Add author names to a set to ensure uniqueness.

- **Purpose**: Dynamically scrape all pages for unique author names.

---

### **Q1**: Extract titles of books with 2-star ratings from "Books to Scrape."

- **Steps**:
  1. Construct page URLs (`https://books.toscrape.com/catalogue/page-{}.html`) dynamically.
  2. Loop through all 50 pages.
  3. Locate book elements (`.product_pod`) and filter those with the `.star-rating.Two` class.
  4. Extract the title of 2-star rated books using the `title` attribute of the `<a>` tag.

- **Purpose**: Identify and list book titles with a 2-star rating.

---

### **Techniques and Concepts Used**:
1. **Requests**:
   - Fetch HTML content from websites.
2. **BeautifulSoup**:
   - Parse HTML.
   - Use CSS selectors (`.class`) for targeted data extraction.
3. **Sets and Lists**:
   - Ensure uniqueness (`set`) or store items (`list`).
4. **Loops**:
   - Navigate multiple pages dynamically.
5. **Condition Checks**:
   - Filter elements based on specific criteria (e.g., class name or content).
6. **Dynamic URL Construction**:
   - Use Python string formatting to construct page URLs.

---

### **Libraries Used**:
1. **`requests`**:
   - Fetch HTML content from URLs.
2. **`BeautifulSoup`**:
   - Parse and navigate HTML content efficiently.

---

### **Outcome**:
This project demonstrates how to scrape, process, and organize web data into meaningful insights (e.g., unique authors, quotes, tags, book titles). It also highlights the importance of handling pagination and filtering content dynamically. 

Code:https://github.com/JIMMYULAHANNAN/Web_Scraping/blob/main/web%20scraping%20exercise%20%20(1).ipynb
