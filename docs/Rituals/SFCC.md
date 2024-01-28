# VARIOUS SFCC TRICKS
 

## Merging staging to your sandbox

1. Go to BM on Staging and select Rituals Headless
2. Open Merchant Tools -> Content -> Exports/Imports
3. Libraries -> Exports and then select Library Headless
4. Export it and download the .xml file
5. Go to your BM on your Sandbox, select Rituals Headless
6. Open Merchant Tools -> Content -> Exports/Imports
7. Libraries -> Imports and then drag in the new .xml file
8. Click next and wait for the process to finish

## Importing Configurations

These are the steps for importing latest data (products, promotions, content pages/things) from Staging on other environments (Sandboxes). Each day, backup is generated and can be imported on our sandboxes. If we need new content stuff on sandboxes, we should do the following steps:
1. Pick any site
2. Administration
3. Site Import & Export
4. Select REMOTE radio button
5. Fill the data (hostname: "staging-shop-rituals.demandware.net", login & password should be from dw.json file)
6. Press CONNECT
7. Pick the latest data (name starts with "backup-sandbox-data-XXXXXXXX.zip", where XXXX represents date & time)
8. Press IMPORT
9. Scroll down on the bottom of the page and notice that process has started
10. Press REFRESH button to check status. Process should take 10-25 minutes, depends on data size.
11. When it's done, status will be "Finished (XXXX data errors)" - where amount of written errors should be ignored.

## Can't pass security when going to store front

1. Enable DW Extension in incognito mode
2. Log in to your sandbox in incognito mode