# jsramverk

## kmom01
By running `npm audit`, we identified 11 vulnerabilities, with 3 being of moderate severity and 8 being of high severity. Each vulnerability, its severity, and the packages affected have been listed below.

### Vulnerabilities

#### 1. debug
- **Severity:** High
- **Affected Versions:** <=2.6.8
- **Description:** The `debug` package is affected by inefficient regular expression complexity vulnerability and Regular Expression Denial of Service (ReDoS).
- **Affected Dependencies:** `express`, `finalhandler`, `send`, `serve-static`

#### 2. fresh
- **Severity:** High
- **Affected Versions:** <0.5.2
- **Description:** The `fresh` package is affected by Regular Expression Denial of Service (ReDoS).

#### 3. mime
- **Severity:** Moderate
- **Affected Versions:** <1.4.1
- **Description:** The `mime` package is affected by Regular Expression Denial of Service (ReDoS) when MIME lookup is performed on untrusted user input.

#### 4. ms
- **Severity:** Moderate
- **Affected Versions:** <2.0.0
- **Description:** The `ms` package, developed by Vercel, is affected by inefficient regular expression complexity vulnerability.

#### 5. node-fetch
- **Severity:** High
- **Affected Versions:** <2.6.7
- **Description:** The `node-fetch` package forwards secure headers to untrusted sites.

#### 6. qs
- **Severity:** High
- **Affected Versions:** <=6.2.3
- **Description:** The `qs` package is vulnerable to Prototype Pollution Protection Bypass and Prototype Pollution.

#### 7. semver
- **Severity:** Moderate
- **Affected Versions:** 6.0.0 - 6.3.0 || 7.0.0 - 7.5.1
- **Description:** The `semver` package is vulnerable to Regular Expression Denial of Service (ReDoS).

### Solution
All issues were resolved by running `npm audit fix`, as suggested in the ouput of the intial audit. Upon running `npm audit` again, no further security vulnerabilities were detected among the installed packages.
