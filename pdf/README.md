# Catalog PDF

## Environment setup

`python3 -m venv venv`
`source venv/bin/activate`
`pip install --upgrade pip`
`pip install -r requirements.txt`

## Generate PDF

1.  Delete the <body> of catalog.html
2.  Go to the [Catalog test site](https://devinstruction.austincc.edu/catalog-test/) and copy the body from that page using Chrome Dev Tools
3.  Paste that into catalog.html
4.  Delete the H1 tag
5.  Copy the following lines and insert them at the top of the first .container div

     <div style="text-align:center; padding:0; margin:0;page-break-after:always;">
    	<img style="width:700px;" src="img/hero.png" />
    </div>

6.  `./search-replace.sh catalog.html`
7.  `source venv/bin/activate` if not already active
8.  `weasyprint -s tables.css ./catalog.html ./catalog2019-20.pdf && open catalog2019-20.pdf`
