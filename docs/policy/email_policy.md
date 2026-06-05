# Policiy for Email Export

To successfully enable and operate Email export within Smart VIU, the following policies and configurations must be ensured:

| polcod                  | polvar       | polval       | rtstr1                       |
|-------------------------|--------------|--------------|---------------------------------|
| USR-SMARTBASE_EMAIL     | DEFAULT-CONFIG   | Key            | Value   |

**Key names and values**:

Configure these key (polval) and values to setup email export:

- `MAIL_SERVER` → `rtstr1` (SMTP host)
- `MAIL_PORT` → `rtnum1` (SMTP port)
- `MAIL_TLS` → `rtnum1` (1/0 enable TLS)
- `MAIL_USER` → `rtstr1` (username)
- `MAIL_PASSWORD`→ `rtstr1` (password)
- `MAIL_SENDER` → `rtstr1` (From address)
- `FEATURE_ENABLED` → `rtnum1` (1/0 feature flag)

After setting up the policies navigate to the SmartViu screen and select the email setting button. 

<div style="text-align: left;">
    <img src="./Attachments/emailsetting.png"
        alt="undirectedmenu"
        style="height: 200px; margin: auto; display: block; cursor: zoom-in;
                border: 2px solid #000000; border-radius: 4px;"
        onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
        ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>

From here you can view your email settings and update them too. 

---