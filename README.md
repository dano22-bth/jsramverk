# jsramverk

## kmom01
### Vulnerabilities
By running `npm audit`, we identified 11 vulnerabilities, with 3 being of moderate severity and 8 being of high severity. Each vulnerability, its severity, and the packages affected have been listed below.

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

------------------------------

### Steps to make the app work
To get the app to work, we used the steps outlined below.

#### Step 1: Obtain an API Key from Trafikverket
First we obtained an API key from Trafikverket by visitng their website, registering an account, and following the instructions there.

#### Step 2: Create a .env File
Next we created a `.env` file in the `backend` directory and added our newly acquired API key using the following format:

```
TRAFIKVERKET_API_KEY=<api-key-here>
```

#### Step 3: Run the Database Reset Script
We then moved to the `backend` folder of the project and exectued the provided script to recreate the database and perform migrations:

```
bash db/reset_db.bash
```

#### Step 4: Start Express
We installed `nodemon` as a devDependency in the project and created an npm script to use it. We then started the Express server by running:

```
npm run dev
```

#### Step 5: Start an HTTP Server on Port 9000
Finally, in order to serve the app, we started a python HTTP server on port 9000 by navigating to the `frontend` directory and running:

```
python3 -m http.server 9000
```

--------------------------

### Framework selection
We decided to go with the `Vue` framework.

--------------------------