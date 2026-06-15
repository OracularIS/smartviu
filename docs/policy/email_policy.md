# Policies for Email Export

To successfully enable and operate Email export within Smart VIU, the following policies and configurations must be ensured:


## Email Configuration Policies

| # | polcod | polvar | polval | Description |
|---|---------|---------|-------------|-------------|
| 1 | **USR-SMARTBASE_EMAIL** | **DEFAULT-CONFIG** | **MAIL_SERVER** | Specifies the SMTP server host used for sending emails. |
| 2 | **USR-SMARTBASE_EMAIL** | **DEFAULT-CONFIG** | **MAIL_PORT** | Specifies the SMTP server port used for email communication. |
| 3 | **USR-SMARTBASE_EMAIL** | **DEFAULT-CONFIG** | **MAIL_TLS** | Controls whether TLS is enabled (`1`) or disabled (`0`) for SMTP connections. |
| 4 | **USR-SMARTBASE_EMAIL** | **DEFAULT-CONFIG** | **MAIL_USER** | Specifies the username used to authenticate with the SMTP server. |
| 5 | **USR-SMARTBASE_EMAIL** | **DEFAULT-CONFIG** | **MAIL_PASSWORD** | Specifies the password used to authenticate with the SMTP server. |
| 6 | **USR-SMARTBASE_EMAIL** | **DEFAULT-CONFIG** | **MAIL_SENDER** | Specifies the sender email address used in outgoing emails. |
| 7 | **USR-SMARTBASE_EMAIL** | **DEFAULT-CONFIG** | **FEATURE_ENABLED** | Controls whether the email feature is enabled (`1`) or disabled (`0`). |

## Policy Structure 

| polcod                  | polvar       | polval       | rtstr1                       |
|-------------------------|--------------|--------------|---------------------------------|
| USR-SMARTBASE_EMAIL     | DEFAULT-CONFIG   | Key            | Value   |


1. **Enable Email Feature**

    | polcod | polvar | polval | rtnum1 |
    |---------|---------|---------|---------|
    | USR-SMARTBASE_EMAIL | DEFAULT-CONFIG | FEATURE_ENABLED | 1 |

    Note: `RTNUM1 = 1` enables email functionality, while `RTNUM1 = 0` disables it.

2. **Mail Password Policy**

    | polcod | polvar | polval | rtstr1 |
    |---------|---------|---------|---------|
    | USR-SMARTBASE_EMAIL | DEFAULT-CONFIG | MAIL_PASSWORD | enter password here |

3. **Mail Port Policy**

    | polcod | polvar | polval | rtnum1|
    |---------|---------|---------|---------|
    | USR-SMARTBASE_EMAIL | DEFAULT-CONFIG | MAIL_PORT | enter port value here |

4. **Mail Sender Policy**
    | polcod | polvar | polval | rtstr1|
    |---------|---------|---------|---------|
    | USR-SMARTBASE_EMAIL | DEFAULT-CONFIG | MAIL_SENDER | enter email here |

5. **Mail Server Policy**
    | polcod | polvar | polval | rtstr1|
    |---------|---------|---------|---------|
    | USR-SMARTBASE_EMAIL | DEFAULT-CONFIG | MAIL_SERVER | enter server name |

6. **Mail TLS Policy**

    | polcod | polvar | polval | rtnum1|
    |---------|---------|---------|---------|
    | USR-SMARTBASE_EMAIL | DEFAULT-CONFIG | MAIL_TLS | 0/1 |

    Note: `RTNUM1 = 1` enables TLS, while `RTNUM1 = 0` disables it.

7. **Mail User Policy**
    | polcod | polvar | polval | rtstr1|
    |---------|---------|---------|---------|
    | USR-SMARTBASE_EMAIL | DEFAULT-CONFIG | MAIL_USER | enter user mail |


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