# 311 Service Requests – Schema Documentation

**Source:** [NYC Open Data (Socrata)](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2020-to-Present/erm2-nwe9/about_data) \
**Dataset ID:** erm2-nwe9  
**Ingestion Method:** API pagination (`$limit` / `$offset`)  
**Update Strategy:** Incremental (cursor-based on `created_date`)

---

## Selected Fields

| Field Name       | Data Type          | Nullable | Description                                                                            |
|------------------|--------------------|----------|----------------------------------------------------------------------------------------|
| `unique_key`     | TEXT               | ❌ | Unique identifier for each 311 request                                                 |
| `created_date`   | FLOATING_TIMESTAMP | ❌ | Date the request was created                                                           |
| `closed_date`    | FLOATING_TIMESTAMP | ✅ | Date the request was closed by responding agency                                       |
| `agency`         | TEXT               | ❌ | Acronym of responding agency                                                           |
| `agency_name`    | TEXT               | ❌ | Full agency name of responding agency                                                  |
| `complaint_type` | TEXT               | ❌ | Describes the topic of the incident or condition and are defined by responding agencies |
| `descriptor`     | TEXT               | ✅ | Provides further detail on the incident or condition                                   |
| `incident_zip`   | TEXT               | ✅ | Location ZIP code of incident                                                          |
| `borough`        | TEXT               | ✅ | Borough of incident                                                                    |
| `status`         | TEXT               | ❌ | Current request status                                                                 |
| `open_data_channel_type`         | TEXT               | ❌ | How the request was submitted to 311 e.g Mobile, Online e.t.c                          |
| `latitude`       | NUMBER             | ✅ | Latitude coordinate                                                                    |
| `longitude`      | NUMBER             | ✅ | Longitude coordinate                                                                   |

---

## Assumptions

- `unique_key` is globally unique per service request
- `created_date` is immutable once published
- Records are append-only (no hard deletes)


