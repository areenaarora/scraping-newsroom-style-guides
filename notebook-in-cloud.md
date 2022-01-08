## Hosting your notebook in the cloud (Areena)\n",
    "\n",
    "If your notebook is located on GitHub at \n",
    "\n",
    "```\n",
    "https://github.com/areenaarora/scraping-newsroom-style-guides/blob/master/all-combined/all-combined.ipynb\n",
    "```\n",
    "\n",
    "you can leverage Google Colab to automatically see it on the cloud by visiting\n",
    "\n",
    "```\n",
    "https://colab.research.google.com/github/areenaarora/scraping-newsroom-style-guides/blob/master/all-combined/all-combined.ipynb\n",
    "```\n",
    "\n",
    "...but it won't work without a little extra work!\n",
    "\n",
    "### Downloading files\n",
    "\n",
    "It needs some files, and we'll need to download them. We could use urlretrieve or requests, but let's cheat and use `wget` (mentioned by Harsha).\n",
    "\n",
    "We want to download [this file](https://github.com/areenaarora/scraping-newsroom-style-guides/blob/master/all-combined/bbc_cleaned.xlsx), but we can't use that URL because it's GitHub's \"look at the file\" page instead of the actual \"download this file\" page. If you click the 'Download' or 'Raw' buttons you'll see the url is actually `https://github.com/areenaarora/scraping-newsroom-style-guides/raw/master/all-combined/bbc_cleaned.xlsx`."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "85aaf078",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "2021-12-16 15:43:45 URL:https://raw.githubusercontent.com/areenaarora/scraping-newsroom-style-guides/master/all-combined/bbc_cleaned.xlsx [156749/156749] -> \"bbc_cleaned.xlsx.2\" [1]\r\n"
     ]
    }
   ],
   "source": [
    "# Do this for every single file you have to download to make\n",
    "# the notebook work\n",
    "!wget -nv https://github.com/areenaarora/scraping-newsroom-style-guides/raw/master/all-combined/bbc_cleaned.xlsx"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "cbd13aea",
   "metadata": {},
   "source": [
    "If you put this at the top of your notebook and then pop it onto GitHub, people who use Colab won't have to try hard to get access to your data!"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "51c320c6",
   "metadata": {},
   "source": [