# Analysis of the purchase of medicine for the public health system in Ecuador

This is a repository that includes an analysis of public procurement for the purchase of medicines for the public health system in Ecuador since 2022, carried out through corporate purchasing mechanisms.

The goal of this project is to understand how corporate purchasing is functioning in Ecuador. For context, in 2022 the government launched this mechanism to centralize the procurement of medicines for the entire public health system, including social security institutions. 

A total of 830 medicines, in various concentrations and commercial presentations (the most commonly prescribed by doctors), were selected for this centralized procurement mechanism. These medicines were included in an official catalog. For the purposes of this analysis, each unique combination of medicine, concentration and presentation will be referred to as an "item."

The analysis conducted in this project revealed several key findings:
1. Procurement processes were launched between 2022 and 2023, during the administration of former President Guillermo Lasso. Under the current government, no new processes have been initiated.
2. Between 2022 and 2023, a total of 986 procurement processes were launched for 830 different items. Several processes failed and had to be relaunched.
3. During the period analyzed, suppliers were awarded contracts for 414 items, while other 414 items did not receive any awarded contracts.
4. There are 116 compounds that failed to secure a contract in any of their available concentrations or commercial presentations.

For this project, I had to build a custom scraper to automatically download all procurement processes. This task was challenging because the website is really old JavaScript and has several limitations. For example, it only allows searches for periods of up to six months and includes a CAPTCHA.

I solved this by developing a scraper that combines Playwright and BeautifulSoup, although it still requires a partially manual step to bypass the CAPTCHA and the search period.

I also applied the skills I’ve acquired in Pandas to clean and analyze the scraped data.

This was done in four Jupyter Notebooks:
1. The first one includes the scraper for the [SERCOP website](https://modulocomprascorporativas.compraspublicas.gob.ec/ProcesoContratacion/compras/PC/buscarProceso.cpe?sg=1#). The Playright scraper first gathers a list of all procurement processes and its urls. Then, it goes inside each URL and gathers the information about each process.
2. The second notebook was used for data cleaning and analysis of the scraped data, dividing the items into two categories: those with awarded contracts and those without (this notebook has not been updated since I updated the scraper).
3. A third notebook dives into the processes that got a contract and merges with information about medicine delivered to public hospitals (not updated either).
4. The fourth notebook includes a new scraper using Playwright to download all the 414 contracts, for fact-checking.

This project is a first exploration of how public procurement of medicines functions within Ecuador’s public healthcare system. However, it still requires more work to have a complete picture of how it is funtioning. Future steps include:
- Updating the analysis.
- Further analysis on the medicines that didn't get contracts awarded, to see if there is a pattern.
- Merging the awarded contracts database with another dataset containing the delivery orders for each item.

This project was developed as part of the LEDE Program, at Columbia Journalism School.