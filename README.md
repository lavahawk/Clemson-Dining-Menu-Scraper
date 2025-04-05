# Clemson Dining Hall Menu Scraper

A lightweight Python script that scrapes and displays real-time menu information from Clemson University's dining halls, with optional Home Assistant integration.
---

## Features

- **Real-time Menu Scraping**  
  Retrieves menus from three dining halls:  
  - Shitter  
  - McAlister  
  - Douthit (Hub)

- **Meal Period Detection**  
  Dynamically fetches breakfast, lunch, and dinner information.

- **Dining Hall Hours**  
  Pulls operating hours for each location.

- **Home Assistant Integration (Optional)**  
  Sends menu data to Home Assistant if enabled.

- **Memory-Optimized**  
  Runs headless, and without a lot of bloat minimizing system resource usage.

- **Common Item Filtering**  
  Skips repetitive or filler menu items to keep displays succinct. like the salad bar fr cuz we dont want to see yogurt 123325 times when we know its there everyday.

- **Scheduled Updates**  
  Automates scraping around meal transitions.

---

## Installation

```bash
pip install selenium webdriver-manager schedule python-dotenv requests
```

## Usage
run the script through python
```
python Clemson_DiningHallMenu
```
## Home Assistant Integration (Optional)
  1. Create a **.env** file in the script directory:
```
    HA_URL=your_home_assistant_url
    HA_TOKEN=your_long_lived_access_token
```
  2. Toggle Home Assistant integration in the script:
   ```
    ENABLE_HOME_ASSISTANT = True  # Set to False to disable
   ```
  3. Add the yaml code included in the Ha_Configuration file to your home assistant configuration file.





## Data Structure
The script returns menu data in the following structure:
```
{
  "location_name": {
    "location": "string",
    "status": "string",
    "meal_period": "string",
    "menu_items": ["string"],
    "last_updated": "string"
  }
}
```
