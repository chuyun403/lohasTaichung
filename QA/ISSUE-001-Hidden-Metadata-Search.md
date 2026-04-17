[UX-BUG-001] Search Interface Returns Unexplained Results Due to Hidden Metadata Matching
Issue Type: UX Defect / Enhancement
Priority: Medium (Impacts user trust and data visibility)
Status: Open
Component: Frontend UI / Search Module

1. Description
When a user utilizes the free-text search input to filter parks, the system correctly executes a broad database query. However, the frontend UI fails to display the specific data field that triggered the match. This creates a confusing user experience where the system appears to be returning incorrect or hallucinated results, degrading user trust in the platform's search integrity.

2. Steps to Reproduce
Navigate to the Park Information Directory.

Ensure district and park dropdowns are set to default (-- 所有行政區 --, -- 所有公園 --).

Enter the character "平" in the text search field.

Observe the filtered results list.

3. Expected Behavior
The UI should clearly indicate to the user why a specific record was returned. If the search query matches the primary display name (Park Name), no additional context is needed. If the match occurs in a secondary, hidden field (e.g., Village, Address, Zoning Code), the UI should surface a contextual label explaining the match.

4. Actual Behavior
The system returns records such as 自立公園 (Zili Park) and (細)公兼兒3 alongside expected matches like 西平公園 (Xiping Park). Because the UI only renders the Park Name and Facility tags, the user has no visual context for why the non-matching titles were included in the results array.

5. Root Cause Analysis (Data Flow)
The search function is operating as designed at the database level but failing at the presentation layer. The backend query is successfully searching across the entire metadata schema for each park, rather than limiting the query to the park_name string.

Specifically, the "anomalous" results are triggered by administrative geographic data:

自立公園 is administratively located within 平和里 (Pinghe Village). The query matched the "平" in the village name.

(細)公兼兒3 is located adjacent to Zhenping Park, heavily implying a geographic metadata match for 鎮平里 (Zhenping Village) or a related street address (e.g., 建平路).

The discrepancy is purely a gap between backend data intelligence and frontend data transparency.

6. Proposed Solution & UX Enhancement
Do not restrict the backend search scope. Broad queries are highly valuable for data discovery. Instead, implement a "Match Context" UI pattern to bridge the gap between the database and the user.

Implementation Steps:

Modify the API Response: Ensure the search API returns a matched_field key in its JSON payload when a text search is executed (e.g., "matched_field": "village_name", "matched_value": "平和里").

Update the UI Component: Add conditional rendering to the park result card.

UX Behavior: If the search keyword matches a field other than the Park Name, render a small, unobtrusive badge or subtext beneath the title.

Example Mockup: 自立公園 (🔍 Match found in location: 平和里)

7. Business Value (Digital Transformation Context)
Implementing this fix transforms a "black box" database query into a transparent, user-centric tool. By surfacing hidden metadata intelligently, we improve system adoption rates, reduce user frustration, and demonstrate that the platform's data architecture is both robust and context-aware.

*** ### How to use this in your portfolio
In your README.md, under a "Quality Assurance & UX Strategy" section, you can write something like:

"During development, I identified a critical UX disconnect where backend database queries were too opaque for the end-user, resulting in 'hidden' metadata matches that looked like bugs. Instead of narrowing the data query, I designed a solution to increase frontend data transparency. See Issue #001: Hidden Metadata Search for my root-cause analysis and proposed data-intelligent solution."