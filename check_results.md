---
name: sunc-fetch-handler
description: Parses sunc.su short links or direct sunc API links, extracts the scrap and key parameters, and queries the weao api to fetch the results.
---

# Sunc Fetch Handler

## Overview
This skill handles the process of resolving short links from `sunc.su` (or parsing direct `sunc.rubis.app` links), extracting the required parameters (`scrap` and `key`), and querying the WEAO API.

## Workflow

1. **Input Link Analysis**:
   * If given a short link (e.g., `https://r.sunc.su/...`), curl or resolve the URL to find the final destination.
   * The resolved URL will contain `scrap` and `key` query parameters (matching the structure of `https://sunc.rubis.app/?scrap=[value]&key=[value]`).

2. **Parameter Extraction**:
   * Extract the `scrap` value.
   * Extract the `key` value.

3. **API Request**:
   * Construct and fetch the request using the WEAO API endpoint format:
     `https://weao.xyz/api/sunc?scrap=[suncScrap]&key=[suncKey]`

4. **Output**:
   * Return the fetched results directly to the user.