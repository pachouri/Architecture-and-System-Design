Read data from the system:  
🔹 Cache aside  
🔹 Read through  
<br/>Write data to the system:  
🔹 Write around  
🔹 Write back  
🔹 Write through

![alt text](https://github.com/pachouri/Architecture-and-System-Design/blob/main/diagram/DB_Caching_Strategies.gif?raw=true)

**Reading Data:**

1. **Cache Aside (Lazy Loading)**:
    - **Process**: The application reads from the cache first. If the data is not in the cache (cache miss), it fetches it from the database, stores it in the cache, and returns it to the user.
    - **Advantages**: Reduces database load by caching frequently requested data.
    - **Disadvantages**: Initial read can be slower (because it fetches from the database), and data can become stale over time.
    - **Example**: If you are requesting user details, the application checks the cache first. If the details aren't there, it fetches them from the database and stores them in the cache for future use.
2. **Read Through**:
    - **Process**: The application always reads through the cache, which is responsible for interacting with the database. If a cache miss occurs, the cache automatically loads the data from the database and serves it to the user.
    - **Advantages**: Simplifies logic in the application, as all reads go through the cache.
    - **Disadvantages**: Can increase the complexity of cache implementation since the cache must handle database interactions.
    - **Example**: In a user profile request, the cache handles fetching data from the database if it’s not present, abstracting the database interaction from the application.

**Writing Data:**

1. **Write Around**:
    - **Process**: The data is written directly to the database and **not** to the cache. The cache will eventually be updated when the data is next read.
    - **Advantages**: Reduces the complexity of updating both the cache and the database.
    - **Disadvantages**: The cache can serve stale data until the next read happens, and there could be a delay in the cache being updated.
    - **Example**: A product’s price is updated directly in the database, but the cached price remains the old one until a new request triggers a cache refresh.
2. **Write Back (Lazy Write)**:
    - **Process**: Data is written to the cache first, and later the cache writes it back to the database asynchronously. Writes to the cache can be batched and then pushed to the database.
    - **Advantages**: Reduces write latency and can batch multiple write operations.
    - **Disadvantages**: If the cache fails before the data is written to the database, data can be lost.
    - **Example**: A user posts a comment, and it’s written to the cache instantly. The cache later writes this comment to the database during the batch update process.
3. **Write Through**:
    - **Process**: The data is written to both the cache and the database at the same time.
    - **Advantages**: Ensures the cache is always up to date with the database, minimizing the chance of serving stale data.
    - **Disadvantages**: Increased write latency, as every write operation is performed on both the cache and the database.
    - **Example**: When a user updates their profile, the updated data is written to both the cache and the database simultaneously.
