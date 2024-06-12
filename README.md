2. Install dependencies:
cd Reapper
pip install -r requirements.txt

## Usage

### Filtering TikTok Posts

To filter TikTok posts based on hashtags, time, and views:

1. Obtain an access token from the TikTok Developer platform.
2. Use the provided scripts to query posts and extract user information.
3. Modify the query parameters as needed to fit your specific use case.

## API Documentation

### TikTok Research API

#### `GET /research/video/query`

- **Description:** Query TikTok videos based on specified criteria.
- **Parameters:**
- `hashtag_name`: Filter by hashtag.
- `create_time`: Filter by post creation time.
- `view_count`: Filter by the number of views.
- **Example:**
```bash
curl -X POST 'https://open.tiktokapis.com/v2/research/video/query' \
-H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
-d '{
     "query": {
         "and": [
             {"operation": "IN", "field_name": "hashtag_name", "field_values": ["exampleHashtag"]},
             {"operation": "GTE", "field_name": "create_time", "field_values": ["2024-01-01T00:00:00Z"]},
             {"operation": "GTE", "field_name": "view_count", "field_values": ["1000"]}
         ]
     },
     "max_count": 100
 }'
