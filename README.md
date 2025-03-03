-#  Streaming Framework

A lightweight **JavaScript framework** designed to simplify **YouTube Live Streaming integration** with seamless **HTML support**. Perfect for embedding live streams, customizing player controls, and managing real-time stream data.
<h2>2️ App Setup</h2>

<pre>
<code class="language-javascript">
const app = express();
const PORT = process.env.PORT || 3000;
app.use(express.json());
</code>
</pre>

<p> This does:</p>
<ul>
  <li>Creates an Express app.</li>
  <li>Sets the server to run on the port from <code>.env</code> or default <code>3000</code>.</li>
  <li>Makes sure it can handle JSON in requests (<code>POST</code>, <code>PUT</code>, etc.).</li>
</ul>

<h2>3 API Endpoints</h2>

<h3>📹 YouTube Data API Routes:</h3>
<p>These are <code>GET</code> routes:</p>

<pre>
<code class="language-javascript">
app.get('/api/videos/:id', async (req, res) => {
    const videoDetails = await getVideoDetails(req.params.id);
    res.json(videoDetails);
});
</code>
</pre>
<p><code>/api/videos/:id</code> — Get info about a video by ID.</p>

<pre>
<code class="language-javascript">
app.get('/api/search', async (req, res) => {
    const videos = await searchVideos(req.query.q);
    res.json(videos);
});
</code>
</pre>
<p><code>/api/search?q=keyword</code> — Search YouTube videos with a keyword.</p>

<pre>
<code class="language-javascript">
app.get('/api/channel/:id', async (req, res) => {
    const channelInfo = await getChannelInfo(req.params.id);
    res.json(channelInfo);
});
</code>
</pre>
<p><code>/api/channel/:id</code> — Get info about a YouTube channel.</p>

<h3>YouTube Live Streaming API Routes:</h3>
<p>These handle live stream creation, updates, and details.</p>

<pre>
<code class="language-javascript">
app.post('/api/live', async (req, res) => {
    const liveStream = await createLiveStream(req.body);
    res.json(liveStream);
});
</code>
</pre>
<p><code>POST /api/live</code> — Create a new live stream (you send stream info in the body).</p>

<pre>
<code class="language-javascript">
app.put('/api/live/:id', async (req, res) => {
    const updatedStream = await updateLiveStream(req.params.id, req.body);
    res.json(updatedStream);
});
</code>
</pre>
<p><code>PUT /api/live/:id</code> — Update an existing live stream (edit details).</p>

<pre>
<code class="language-javascript">
app.get('/api/live/:id', async (req, res) => {
    const liveStreamDetails = await getLiveStreamDetails(req.params.id);
    res.json(liveStreamDetails);
});
</code>
</pre>
<p><code>GET /api/live/:id</code> — Get details of a specific live stream.</p>

<h2> Start the Server</h2>

<pre>
<code class="language-javascript">
app.listen(PORT, () => {
    console.log(`Server is running on http://localhost:${PORT}`);
});
</code>
</pre>

<p> This launches the backend server on the given port and starts listening for incoming API requests.</p>

<h2>🚀 What is this app good for?</h2>
<ul>
  <li> Building your own YouTube streaming manager.</li>
  <li> Fetching video or channel data easily.</li>
  <li> Handling live streaming operations without using the YouTube dashboard manually.</li>
  <li> Could be combined with a frontend (HTML/JS) to create a full streaming web app.</li>
</ul>

<h2> Summary</h2>
<p>This backend is like your own custom YouTube control center, where:</p>
<ul>
  <li>You can search YouTube.</li>
  <li>Get details on videos and channels.</li>
  <li>Start and manage live streams.</li>
</ul>
<p>All through your own API! 🌐</p>


##  Project Structu
