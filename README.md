# Proxy Explorer 1.0

**Discover public proxy candidates, measure response time, and inspect their observed anonymity.**

Proxy Explorer is a Windows x64 desktop application by Paolo Monti, with a modern,
flat interface and an integrated user guide.

## Features

- Discover candidates from ProxyScrape or GeoNode.
- Filter provider-reported uptime from **80% to 100%**, in increments of 1%.
- Select **10 to 200 candidates**, in increments of 10.
- Test proxies concurrently, with progress percentage and cancellation.
- View discovered, selected and working proxy counts.
- Inspect connection status, response time and observed anonymity.
- Sort results by clicking column headings.
- Copy a proxy's address, port or `address:port` using the context menu.
- Import saved CSV or TXT lists and run fresh tests.
- Export working results to CSV or TXT in three formats.
- Open the integrated guide with **F1**.

## Requirements

- Windows with support for x64 applications.
- Internet access for discovery and live tests.
- For portable use, keep `ProxyExplorer.exe` and `ProxyExplorer.chm` together.

## Installation

Run `ProxyExplorer-1.0-Win64-Setup.exe` from the release package.

1. Choose **current user** or **all users**.
2. Read the License Agreement and select **I accept the agreement** to continue.
3. Choose the destination and, optionally, a desktop shortcut.
4. Complete setup and launch Proxy Explorer.

The default current-user installation does not require administrator rights.
Installing for all users requires Windows administrative authorization.
Setup installs the application and CHM guide, plus its uninstaller.
Without accepting the agreement, installation cannot proceed.

## Quick start

1. Choose a discovery provider.
2. Set **Minimum uptime %** and **Maximum candidates**.
3. Click **Discover and test**. During testing, this becomes **Cancel test**.
4. Read **Status**, **Test ms** and **Observed anonymity** together.
5. Choose **Export usable list** to save working results.

To retest saved proxies, click **Load list and test** and select a CSV or TXT file.
Right-click a populated row to copy its values or clear the list.
Clearing is disabled during a test; the context menu is unavailable on an empty list.

## Import and export formats

| Format | Example |
| --- | --- |
| Address and port | `192.0.2.10:8080` |
| Address and port, anonymity | `192.0.2.10:8080,Anonymous` |
| Separate address, port and anonymity | `192.0.2.10,8080,Anonymous` |

CSV headers are optional; TXT exports contain no header. Files use UTF-8.
Only working rows are exported, including any Transparent or Unknown results.
Export is not restricted to anonymous proxies.

Import detects these formats automatically, with or without a header.
Use one proxy per line and a consistent format throughout the file.
Enclose IPv6 addresses in square brackets.
Files are limited to 1 MB and 200 unique proxies.
Saved anonymity values are historical and are not reused as new test results.

## Understanding results

Provider uptime, latency and anonymity are third-party metadata.
Proxy Explorer separately observes identity responses through each candidate
and checks for address disclosure and proxy-related headers.

- **Transparent:** the test detected disclosure of the direct public address.
- **Anonymous:** the address was not detected as disclosed, but proxy-related signals were observed.
- **Elite:** the test did not detect address disclosure or proxy-related signals.
- **Unknown:** there was insufficient evidence to classify the response.

**Test ms** measures request latency, not download bandwidth.
Results depend on the connection, endpoint and time of the test.
An Elite result does not prove complete anonymity, privacy or security.

## Safety and responsible use

Public proxies are untrusted and may disappear, log traffic or expose data.
Do not send passwords, financial information or other sensitive data through
untrusted proxies. A public listing or successful test is not permission to
use a third-party system. Use only systems you are authorized to access and
comply with applicable laws and service terms.

## Help

Spin-control values and window dimensions are saved on exit and restored on
the next launch, including the maximized state. Preferences are stored per user
in `%LOCALAPPDATA%\Proxy Explorer\settings.ini`; results must still be exported
explicitly. Hover over controls for help tooltips, with longer text on multiple lines.

Press **F1**, click **Press F1 for help**, or open the installed Start-menu guide.
The guide covers controls, results, exports and troubleshooting.
The guide opened by the application closes when Proxy Explorer closes.

## License

Copyright (C) 2026 Paolo Monti. All rights reserved.

- Free of charge for **non-commercial use**.
- **Commercial use requires prior written permission from Paolo Monti**.
- The software and supplied components **may not be modified**, subject to mandatory law.
- Provided **as is**, with the warranty disclaimer and liability limitations stated in the license.

Read [LICENSE.md](LICENSE.md) for the complete, controlling terms.
This is a restrictive license, not an open-source license.
Publication on GitHub does not grant additional modification or commercial-use rights.
