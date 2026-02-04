Here’s a polished version of your BeatHub Design Document with the defended design decisions filled in clearly:

BeatHub Design Document
1. Data Relationships
- Artist: Parent entity.
- Album: References Artist.
- Song: References Album and Artist.
- User: Independent entity.
- Playlist: References User and contains an array of Song references.
2. Design Decisions (Defend Your Code)
Q: Why did you reference Songs in the Playlist instead of embedding them?
- A: Referencing Songs ensures that any updates to a Song’s details (such as a title change, updated metadata, or corrected artist attribution) are automatically reflected across all playlists. If Songs were embedded, every playlist containing that Song would need to be manually updated, leading to data inconsistency and duplication. This approach also reduces storage overhead and improves maintainability.
Q: Why did you reference the Artist in the Song model?
- A: Directly referencing the Artist in the Song model allows for efficient queries like “Find all songs by Daft Punk” without needing to traverse through Albums first. This design supports faster lookups, simplifies query logic, and makes the system more flexible for cases where Songs may exist outside of traditional album structures (e.g., singles or collaborations).
