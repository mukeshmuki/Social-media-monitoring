# telegram-piracy-monitoring

The objective is to identify the telegram channels, messages, conversations, invoices where the business content, subscriptions are being sold and pirated by external parties.

Techniques and Languages used:
	Python, Telegram API, Scrapping, NLP - Text processing and Manipulation, Image text extraction.

Finding the fraudulent telegram channels through an automated means:-

How it’s done manually:
	Open telegram web or mobile app and search with potential keywords like ’stock market’.
	There are some channels shown in search results. To proceed further, we need to manually join the respective channels to go through the messages and images.

1. The same is achieved through automation. Keywords are given as input to our application. 
2. Our application takes the search term and using the api scraping throws the following channels output which is same and better than the manual output obtained:
3. Next step is join the channels as a member which is mandatory to scrape through the content. This is achieved through automation as well.

Once we join the channel, we can scrape through the messages, download the images, scrape the content, perform the text analysis and find out the fraudulent content and channels.

Process:

1. Build a list of potential keywords (’stock market updates’, ’stock market tips' etc.)
2. Run these keywords through the first part of the application to get a list of potential channels.
3. These channels are maintained in a data repository to avoid duplicacy.
4. Once the channels data repository is built, join the channels and scrape the messages and download the images in individual separate folders.
5. Run our image processing and text extraction models on the messages, images and text content.
6. Identify the potential fraudulent channels and highlight them.
7. Save the fraudulent content like messages, content in a separate folder under the respective channel names.
8. Perform analysis and derive necessary business insights.

Challenges:
1. Private channels scrapping.

We have built a full fledged application which takes input from a Google sheet. The code will be set to run in the background and the user has to change the options in the Google sheet to trigger the application. When the user input “Run the Application” is set to “Yes” the application will start running for the ‘search' term entered.
All the relevant channels will be scrapped and kept in the sheet ‘found_channels’. And the application will wait for the input before starting scrapping the channel information.
The channel information will be scrapped, text images will be scrapped, images are downloaded to a folder, and for all the corresponding images the text scraping is done and the NLP algorithms are run to find the potential fraudulent content.

The final content will be

1. Text messages extraction file with potential fraudulent keywords flagged.
2. All the images of the channel scrapped in a folder
3. Image messages with text scrapped and keywords flagged.
4. List of all the keyword flagged images in a separate folder.

Now all the above files will be zipped and sent to a slack channel where the end user can download the final files and folder.

