### List of Ban F&O

<pre>
## Securities in BAN Period

def ban_securities():
    try:
        url = "https://www.nseindia.com/archives/fo/sec_ban/fo_secban_" + datetime.datetime.today().strftime('%d%m%Y') + ".csv"
        s=requests.get(url).content
        df=pd.read_csv(io.StringIO(s.decode('utf-8')))
        cols= df.columns.get_values()
    except:       
        print("404 - Page not Found")
    return df[cols[0]]


ban_securities()
</pre>
