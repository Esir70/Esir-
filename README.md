<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#08783d">
<title>ESIR | All-in-One Hybrid Platform</title>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
:root{--green:#08783d;--bright:#16a05a;--mint:#e8f8ee;--pale:#f5faf6;--line:#dce8df;--ink:#17251c;--muted:#6a7a70;--white:#fff;--shadow:0 12px 35px #173f2410}
*{box-sizing:border-box}
body{margin:0;background:#edf3ef;color:var(--ink);font-family:Inter,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif}
button,input,textarea,select{font:inherit}
button{cursor:pointer}
button:focus-visible,input:focus-visible,textarea:focus-visible{outline:3px solid #76d99b;outline-offset:2px}
.app{min-height:100vh;max-width:1600px;margin:auto;background:#fff;display:grid;grid-template-columns:76px 310px minmax(0,1fr);box-shadow:var(--shadow)}
.rail{background:#f6fbf7;border-right:1px solid var(--line);display:flex;flex-direction:column;align-items:center;padding:18px 10px;gap:13px}
.brandmark{height:44px;width:44px;border-radius:15px;background:var(--green);color:white;display:grid;place-items:center;font-size:23px;font-weight:900;margin-bottom:15px}
.railbtn{border:0;background:transparent;width:48px;height:48px;border-radius:15px;font-size:21px;color:#62766a;position:relative;display:flex;flex-direction:column;align-items:center;justify-content:center}
.railbtn.active,.railbtn:hover{background:#dff6e7;color:var(--green)}
.railbtn small{display:block;font-size:9px;font-weight:700;margin-top:1px}
.rail-spacer{flex:1}
.sidebar{border-right:1px solid var(--line);min-width:0;display:flex;flex-direction:column;background:#fff}
.side-head{padding:21px 18px 12px;display:flex;justify-content:space-between;align-items:center}
.side-head h1{margin:0;font-size:1.42rem;letter-spacing:-.04em}
.round{border:0;background:#e7f7ec;color:var(--green);width:36px;height:36px;border-radius:50%;font-size:19px}
.searchbox{margin:0 15px 12px;background:#f2f6f3;border-radius:12px;display:flex;gap:8px;align-items:center;padding:0 12px}
.searchbox input{border:0;outline:0;background:transparent;width:100%;padding:12px 0;font-size:.88rem}
.filters{display:flex;gap:7px;padding:0 15px 12px;overflow:auto}
.filter{border:1px solid var(--line);border-radius:99px;background:#fff;padding:6px 11px;font-size:.78rem;white-space:nowrap;color:#52665a}
.filter.active{background:#dff6e7;color:var(--green);border-color:#dff6e7;font-weight:750}
.list{overflow:auto}
.person{width:100%;border:0;background:white;text-align:left;display:flex;gap:12px;align-items:center;padding:12px 16px;border-top:1px solid #f0f4f1}
.person:hover,.person.active{background:#eff9f2}
.avatar{width:46px;height:46px;border-radius:50%;display:grid;place-items:center;background:#e3f6e9;font-size:22px;flex-shrink:0}
.person-copy{min-width:0;flex:1}
.person-top{display:flex;justify-content:space-between;gap:6px;font-size:.9rem;font-weight:750}
.person-preview{font-size:.79rem;color:var(--muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;margin-top:4px}
.time{font-size:.68rem;color:var(--muted);font-weight:500}
.unread{background:var(--bright);color:white;border-radius:50%;font-size:.68rem;min-width:18px;height:18px;display:grid;place-items:center;margin-top:4px}
.main{min-width:0;display:flex;flex-direction:column;min-height:100vh}
.topbar{height:72px;border-bottom:1px solid var(--line);display:flex;align-items:center;justify-content:space-between;padding:0 24px;gap:15px}
.top-title{display:flex;align-items:center;gap:12px;min-width:0}
.top-title h2{font-size:1rem;margin:0}
.top-title p{font-size:.76rem;color:var(--muted);margin:4px 0 0}
.top-actions{display:flex;gap:8px}
.iconbtn{border:0;background:#f1f7f3;border-radius:11px;width:38px;height:38px;color:var(--green);font-size:18px;display:grid;place-items:center}
.view{display:none;flex:1;min-height:0}
.view.active{display:flex;flex-direction:column}
.chat-bg{flex:1;min-height:320px;padding:25px clamp(15px,4vw,55px);overflow:auto;background-color:#f7fbf8;background-image:radial-gradient(#d9eadf 0.65px,transparent .65px);background-size:17px 17px}
.daytag{width:max-content;margin:0 auto 18px;background:#fff;padding:7px 12px;border-radius:9px;font-size:.72rem;color:var(--muted);box-shadow:0 2px 7px #00000008}
.msg{max-width:min(78%,510px);padding:11px 13px;border-radius:13px;background:#fff;margin:9px 0;box-shadow:0 2px 5px #183d2309;font-size:.89rem;line-height:1.45;overflow-wrap:anywhere}
.msg.mine{margin-left:auto;background:#d8f8e2;border-top-right-radius:4px}
.msg:not(.mine){border-top-left-radius:4px}
.msg .stamp{display:block;text-align:right;color:#74867a;font-size:.65rem;margin-top:5px}
.composer{padding:13px 18px;display:flex;align-items:center;gap:9px;border-top:1px solid var(--line);background:#fff}
.composer textarea{flex:1;resize:none;max-height:120px;min-height:43px;border:0;border-radius:13px;background:#f2f7f3;padding:12px;outline:0}
.send{width:43px;height:43px;border:0;border-radius:50%;background:var(--green);color:#fff;font-size:18px;display:grid;place-items:center}
.helperline{padding:0 20px 10px;color:#819087;font-size:.72rem}
.panel-scroll{padding:25px;overflow:auto;flex:1}
.welcome{border-radius:23px;padding:30px;background:linear-gradient(120deg,#e5faeb,#f5fff7);display:flex;align-items:center;justify-content:space-between;gap:20px;margin-bottom:22px}
.welcome h2{font-size:clamp(1.6rem,3vw,2.6rem);letter-spacing:-.045em;margin:0 0 10px}
.welcome p{color:var(--muted);line-height:1.6;margin:0;max-width:590px}
.pill{display:inline-block;background:white;color:var(--green);padding:7px 11px;border-radius:99px;font-size:.75rem;font-weight:800;margin-bottom:12px}
.welcome-emoji{font-size:clamp(3.2rem,7vw,6rem);flex-shrink:0}
.section-title{display:flex;justify-content:space-between;align-items:center;gap:12px;margin:22px 0 14px}
.section-title h3{margin:0;font-size:1.1rem}
.muted{color:var(--muted)}
.small{font-size:.82rem}
.btn{border:0;border-radius:11px;background:var(--green);color:#fff;padding:10px 14px;font-weight:750}
.btn.light{background:#e5f7eb;color:var(--green)}
.btn.outline{background:white;color:var(--green);border:1px solid #c9e7d2}
.cards{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:13px}
.feature{padding:19px;border:1px solid var(--line);border-radius:17px;background:white;min-height:150px}
.feature .emoji{font-size:25px}
.feature h4{margin:13px 0 6px;font-size:.98rem}
.feature p{margin:0;color:var(--muted);font-size:.83rem;line-height:1.5}
.feature button{margin-top:14px}
.story-row{display:flex;gap:15px;overflow:auto;padding:5px 1px 12px}
.story{border:0;background:transparent;min-width:82px;display:flex;flex-direction:column;align-items:center;gap:7px;color:var(--ink);font-size:.76rem}
.story-ring{height:66px;width:66px;border-radius:50%;padding:3px;border:2px solid var(--bright);display:grid;place-items:center}
.story-ring span{height:100%;width:100%;border-radius:50%;display:grid;place-items:center;background:#e5f8eb;font-size:26px}
.story.add .story-ring{border:2px dashed #8acba0}
.story.add .story-ring span{background:#f5fbf6;color:var(--green)}
.formrow{display:flex;gap:9px;flex-wrap:wrap;margin:15px 0}
.field{border:1px solid var(--line);background:white;border-radius:11px;padding:11px 12px;min-width:0;flex:1}
.field.full{width:100%;flex-basis:100%}
.status-card,.group-card,.community-card,.result-card{border:1px solid var(--line);border-radius:16px;padding:17px;background:#fff;margin:10px 0}
.status-card{background:linear-gradient(120deg,#e8faee,#fff)}
.status-text{font-size:1.05rem;line-height:1.5;margin:10px 0}
.map-search{display:flex;gap:8px;margin:16px 0}
.map-search input{flex:1;min-width:0;border:1px solid var(--line);border-radius:12px;padding:12px}
.mapframe{width:100%;height:360px;border:1px solid var(--line);border-radius:17px;background:#edf6ef}
.map-note{font-size:.78rem;color:var(--muted);line-height:1.5;margin-top:9px}
.call-card{display:flex;align-items:center;gap:13px;border:1px solid var(--line);padding:14px;border-radius:15px;margin:10px 0}
.call-card .avatar{width:42px;height:42px}
.call-card .grow{flex:1}
.empty{padding:35px;text-align:center;color:var(--muted)}
.toast{position:fixed;bottom:20px;left:50%;transform:translate(-50%,20px);opacity:0;transition:.2s;background:#153c27;color:#fff;padding:12px 17px;border-radius:12px;z-index:60;max-width:90vw;text-align:center;pointer-events:none}
.toast.show{opacity:1;transform:translate(-50%,0)}
@media(max-width:1000px){.app{grid-template-columns:64px 270px minmax(0,1fr)}.cards{grid-template-columns:repeat(2,minmax(0,1fr))}.topbar{padding:0 16px}.panel-scroll{padding:18px}}
@media(max-width:720px){.app{display:grid;grid-template-columns:1fr;grid-template-rows:1fr 65px}.rail{position:fixed;z-index:8;bottom:0;left:0;right:0;height:65px;flex-direction:row;justify-content:space-around;padding:5px 8px;border-top:1px solid var(--line);border-right:0;background:#fff}.brandmark,.rail-spacer{display:none}.railbtn{width:47px;height:49px;font-size:19px}.sidebar{display:none}.main{min-height:calc(100vh - 65px);grid-row:1}.topbar{height:64px}.panel-scroll{padding:15px}.welcome{padding:22px}.welcome-emoji{font-size:3rem}.cards{grid-template-columns:1fr 1fr}.feature{padding:15px}.chat-bg{padding:18px 13px}.msg{max-width:88%}.composer{padding:10px}.mapframe{height:310px}}
@media(max-width:430px){.cards{grid-template-columns:1fr}.welcome-emoji{display:none}.top-actions .iconbtn:nth-child(2){display:none}.feature{min-height:0}.section-title h3{font-size:1rem}}
</style>
</head>
<body>

  <!-- ================= AUTH ONBOARDING MODAL ================= -->
  <div id="authOverlay" class="fixed inset-0 z-50 bg-gray-950/90 backdrop-blur-sm flex items-center justify-center p-4">
    <div class="bg-white border border-emerald-100 rounded-2xl p-6 w-full max-w-sm shadow-2xl space-y-4">
      <div class="text-center space-y-2">
        <div class="w-14 h-14 bg-emerald-600 text-white rounded-2xl flex items-center justify-center mx-auto text-2xl font-black shadow-md">
          E
        </div>
        <h1 class="text-2xl font-extrabold tracking-tight text-gray-900">Welcome to ESIR</h1>
        <p class="text-xs text-gray-500">All-in-one messaging, status, maps & tools platform.</p>
      </div>

      <div class="space-y-3">
        <div>
          <label class="text-xs font-semibold text-gray-600 block mb-1">Choose Username</label>
          <div class="flex gap-2">
            <input type="text" id="usernameInput" placeholder="Enter username..." 
              class="w-full bg-gray-50 border border-gray-200 rounded-xl px-3 py-2 text-sm text-gray-800 focus:outline-none focus:border-emerald-600 transition">
            <button onclick="randomizeUsername()" class="bg-emerald-50 border border-emerald-200 hover:bg-emerald-100 px-3 py-2 rounded-xl text-xs text-emerald-700 font-bold shrink-0">
              <i class="fa-solid fa-dice"></i>
            </button>
          </div>
        </div>

        <button onclick="loginUser()" class="w-full bg-emerald-700 hover:bg-emerald-800 text-white font-bold py-2.5 rounded-xl text-sm transition shadow-lg shadow-emerald-700/20">
          Continue to Workspace →
        </button>

        <button onclick="expressGuestLogin()" class="w-full bg-gray-100 hover:bg-gray-200 text-gray-700 font-semibold py-2.5 rounded-xl text-sm transition">
          ⚡ Instant Guest Access
        </button>
      </div>
      <p class="text-[10px] text-center text-gray-400">No passwords required · Local workspace session</p>
    </div>
  </div>

  <!-- ================= MAIN HYBRID APP CONTAINER ================= -->
  <div id="appContainer" class="app hidden">
    <!-- RAIL NAVIGATION -->
    <aside class="rail" aria-label="Main navigation">
      <div class="brandmark">E</div>
      <button class="railbtn active" data-view="chats" title="Chats">💬<small>Chats</small></button>
      <button class="railbtn" data-view="status" title="Status">◉<small>Status</small></button>
      <button class="railbtn" data-view="calls" title="Calls">☎<small>Calls</small></button>
      <button class="railbtn" data-view="communities" title="Communities">♧<small>Groups</small></button>
      <button class="railbtn" data-view="maps" title="Maps">⌖<small>Maps</small></button>
      <button class="railbtn" data-view="discover" title="Discover">✦<small>More</small></button>
      <div class="rail-spacer"></div>
      <button class="railbtn" data-view="settings" title="Settings">⚙<small>Settings</small></button>
    </aside>

    <!-- CHAT SIDEBAR -->
    <aside class="sidebar">
      <div class="side-head">
        <h1 id="sideTitle">Chats</h1>
        <button class="round" onclick="newChat()" title="New chat">＋</button>
      </div>
      <label class="searchbox">
        <span>⌕</span>
        <input id="chatSearch" placeholder="Search chats" oninput="filterChats(this.value)" aria-label="Search chats">
      </label>
      <div class="filters">
        <button class="filter active" onclick="setFilter(this,'all')">All</button>
        <button class="filter" onclick="setFilter(this,'unread')">Unread</button>
        <button class="filter" onclick="setFilter(this,'groups')">Groups</button>
      </div>
      <div class="list" id="chatList"></div>
    </aside>

    <!-- MAIN DISPLAY VIEW -->
    <main class="main">
      <div class="topbar">
        <div class="top-title">
          <div class="avatar" id="topAvatar">👋</div>
          <div>
            <h2 id="topTitle">ESIR Hybrid Hub</h2>
            <p id="topSubtitle">Online · Interactive platform</p>
          </div>
        </div>
        <div class="top-actions">
          <button class="iconbtn" title="Search" onclick="showToast('Search active using sidebar filters.')">⌕</button>
          <button class="iconbtn" title="Call" onclick="showToast('Initiating call preview...')"><i class="fa-solid fa-phone text-xs"></i></button>
          <button class="iconbtn" title="User Settings" onclick="switchView('settings')"><i class="fa-solid fa-user-gear text-xs"></i></button>
        </div>
      </div>

      <!-- VIEW 1: CHATS -->
      <section class="view active" id="view-chats">
        <div class="chat-bg" id="messages"></div>
        <div class="helperline">Single-file hybrid prototype: Local messages persist in browser memory.</div>
        <form class="composer" id="messageForm">
          <button type="button" class="iconbtn" onclick="sendPollPrompt()" title="Create Poll"><i class="fa-solid fa-square-poll-vertical"></i></button>
          <textarea id="messageInput" rows="1" placeholder="Type a message..." aria-label="Type a message"></textarea>
          <button class="send" type="submit" aria-label="Send message">➤</button>
        </form>
      </section>

      <!-- VIEW 2: STATUS -->
      <section class="view" id="view-status">
        <div class="panel-scroll">
          <div class="welcome">
            <div>
              <span class="pill">STATUS & STORIES</span>
              <h2>Share moments instantly.</h2>
              <p>Post custom text updates or stories visible to your contacts in this session.</p>
            </div>
            <div class="welcome-emoji">◉</div>
          </div>
          <div class="section-title">
            <h3>Recent updates</h3>
            <span class="muted small">Active stories</span>
          </div>
          <div class="story-row" id="storyRow"></div>
          <div class="section-title">
            <h3>Create a status</h3>
          </div>
          <form id="statusForm">
            <textarea class="field full" id="statusInput" rows="3" placeholder="What is happening today?" maxlength="280"></textarea>
            <div class="formrow">
              <select class="field" id="statusAudience" aria-label="Status audience">
                <option>My contacts</option>
                <option>Close friends</option>
                <option>Public</option>
              </select>
              <button class="btn" type="submit">＋ Share status</button>
            </div>
          </form>
          <div id="myStatus"></div>
        </div>
      </section>

      <!-- VIEW 3: CALLS -->
      <section class="view" id="view-calls">
        <div class="panel-scroll">
          <div class="welcome">
            <div>
              <span class="pill">CALLS</span>
              <h2>Voice & Video Connect</h2>
              <p>Review call logs and start interactive audio or video simulation streams.</p>
            </div>
            <div class="welcome-emoji">☎</div>
          </div>
          <div class="section-title">
            <h3>Recent calls</h3>
            <button class="btn light" onclick="showToast('Simulating outgoing audio call...')">＋ Start a call</button>
          </div>
          <div id="callList"></div>
        </div>
      </section>

      <!-- VIEW 4: COMMUNITIES -->
      <section class="view" id="view-communities">
        <div class="panel-scroll">
          <div class="welcome">
            <div>
              <span class="pill">GROUPS & COMMUNITIES</span>
              <h2>Collaborate & Coordinate</h2>
              <p>Organize group chats for school units, work teams, or neighborhoods in one unified place.</p>
            </div>
            <div class="welcome-emoji">♧</div>
          </div>
          <div class="section-title">
            <h3>Your groups</h3>
            <button class="btn" onclick="createGroup()">＋ New group</button>
          </div>
          <div id="groupList"></div>
          <div class="section-title">
            <h3>Discover communities</h3>
          </div>
          <div id="communityList"></div>
        </div>
      </section>

      <!-- VIEW 5: MAPS -->
      <section class="view" id="view-maps">
        <div class="panel-scroll">
          <div class="welcome">
            <div>
              <span class="pill">INTEGRATED MAPS</span>
              <h2>Location & Route Search</h2>
              <p>Find locations and instantly share map pins into active chat channels.</p>
            </div>
            <div class="welcome-emoji">⌖</div>
          </div>
          <form class="map-search" id="mapForm">
            <input id="mapQuery" placeholder="Search a place, e.g. Nairobi, Kenya" value="Nairobi, Kenya" aria-label="Search map location">
            <button class="btn" type="submit">Search map</button>
          </form>
          <iframe class="mapframe" id="mapFrame" title="OpenStreetMap preview" loading="lazy" src="https://www.openstreetmap.org/export/embed.html?bbox=36.7%2C-1.35%2C37.0%2C-1.15&layer=mapnik"></iframe>
          <div class="formrow">
            <button class="btn light" type="button" onclick="useMyArea()">⌖ Use default area</button>
            <button class="btn outline" type="button" onclick="shareMap()">↗ Share map to active chat</button>
            <button class="btn outline" type="button" onclick="openMapExternal()">Open full map ↗</button>
          </div>
        </div>
      </section>

      <!-- VIEW 6: DISCOVER -->
      <section class="view" id="view-discover">
        <div class="panel-scroll">
          <div class="welcome">
            <div>
              <span class="pill">DISCOVER</span>
              <h2>Ecosystem Tools & Services</h2>
              <p>Integrated tools, AI assistant, marketplace options, and language utilities.</p>
            </div>
            <div class="welcome-emoji">✦</div>
          </div>
          <div class="cards">
            <article class="feature"><div class="emoji">🏪</div><h4>Local Businesses</h4><p>Browse verified vendors and shops directly.</p><button class="btn light" onclick="showToast('Business directory loaded.')">Explore</button></article>
            <article class="feature"><div class="emoji">🤖</div><h4>ESIR AI Companion</h4><p>Get instant answers, smart summaries, and ideas.</p><button class="btn light" onclick="openAIChat()">Chat with AI</button></article>
            <article class="feature"><div class="emoji">🌍</div><h4>Language Translation</h4><p>Translate messages between English, Swahili, and more.</p><button class="btn light" onclick="showToast('Translation module ready.')">Translate</button></article>
            <article class="feature"><div class="emoji">🛍️</div><h4>Marketplace Orders</h4><p>Track order receipts directly inside chat logs.</p><button class="btn light" onclick="showToast('Order system active.')">Orders</button></article>
            <article class="feature"><div class="emoji">📅</div><h4>Schedules & Polls</h4><p>Organize group decisions and event reminders.</p><button class="btn light" onclick="sendPollPrompt()">Create Poll</button></article>
            <article class="feature"><div class="emoji">🛡️</div><h4>Security & Privacy</h4><p>Manage audience rules and chat encryption options.</p><button class="btn light" onclick="switchView('settings')">Settings</button></article>
          </div>
        </div>
      </section>

      <!-- VIEW 7: SETTINGS -->
      <section class="view" id="view-settings">
        <div class="panel-scroll">
          <div class="welcome">
            <div>
              <span class="pill">SETTINGS</span>
              <h2>Preferences & Security</h2>
              <p>Configure account parameters, data usage, and safety controls.</p>
            </div>
            <div class="welcome-emoji">⚙</div>
          </div>
          <div class="group-card">
            <h3>🔒 Privacy & Security</h3>
            <label class="block mt-2"><input type="checkbox" checked> Enable Link Warnings</label>
            <label class="block mt-2"><input type="checkbox" checked> Block Unknown Group Invites</label>
          </div>
          <div class="group-card">
            <h3>🔔 Notifications</h3>
            <label class="block mt-2"><input type="checkbox" checked> Sound Alerts</label>
            <label class="block mt-2"><input type="checkbox"> Mute Community Announcements</label>
          </div>
          <div class="group-card">
            <h3>👤 Active Account</h3>
            <p id="settingsUsername" class="text-sm font-bold text-emerald-700 mt-1">User: Guest</p>
            <button onclick="logout()" class="btn outline mt-3 text-red-600 border-red-200">Logout Session</button>
          </div>
        </div>
      </section>
    </main>
  </div>

  <div class="toast" id="toast" role="status" aria-live="polite"></div>

  <!-- ================= LOGIC SCRIPT ================= -->
  <script>
    let currentUser = localStorage.getItem('esir_hybrid_user') || '';
    let activeChat = 1;
    let filterMode = 'all';
    let customStatuses = [];
    let customGroups = [];

    const sampleUsernames = ['NovaCoder', 'SwiftPanda', 'ApexDeveloper', 'EsirMember'];

    const chats = [
      { id: 1, name: 'Amina', avatar: '👩🏽', preview: 'Can you send me the location?', time: '10:42', unread: 2, type: 'person', messages: [['them', 'Hey! Are we still meeting later?', '10:39'], ['mine', 'Yes, that works for me.', '10:40'], ['them', 'Can you send me the location?', '10:42']] },
      { id: 2, name: 'ESIR AI Assistant', avatar: '🤖', preview: 'Ask me anything about ESIR!', time: '10:30', unread: 0, type: 'ai', messages: [['them', 'Hello! I am ESIR AI Assistant. How can I help you today?', '10:30']] },
      { id: 3, name: 'Family Group', avatar: '🏡', preview: 'Mum: Sunday lunch at 1 pm', time: '10:20', unread: 3, type: 'group', messages: [['them', 'Mum: Sunday lunch at 1 pm 🍲', '10:17'], ['them', 'I will bring juice.', '10:19'], ['mine', 'Sounds good!', '10:20']] },
      { id: 4, name: 'Ruiru Community', avatar: '🌳', preview: 'Brian: road update near the market', time: '09:56', unread: 0, type: 'group', messages: [['them', 'Brian: road update near the market — please allow extra time.', '09:56']] },
      { id: 5, name: 'Shop Mtaa', avatar: '🛍️', preview: 'Your order is ready for pickup', time: 'Yesterday', unread: 0, type: 'business', messages: [['them', 'Hello! Your order is ready for pickup.', 'Yesterday'], ['mine', 'Thank you for the update.', 'Yesterday']] }
    ];

    const communities = [
      ['🏫', 'Ruiru Study Circle', 'Learning and study sessions', '1.2k members'],
      ['🌱', 'Neighborhood Help', 'Local updates and recommendations', '840 members'],
      ['💻', 'Kenya Creators Hub', 'Share projects, skills, and ideas', '2.4k members']
    ];

    const calls = [
      ['👩🏽', 'Amina', 'Incoming voice call · Today, 10:12'],
      ['🧑🏾', 'Brian', 'Outgoing video call · Yesterday'],
      ['🏡', 'Family Group', 'Group call · Monday']
    ];

    function init() {
      if (currentUser) {
        showApp();
      } else {
        randomizeUsername();
      }
    }

    function randomizeUsername() {
      const rand = sampleUsernames[Math.floor(Math.random() * sampleUsernames.length)] + Math.floor(Math.random() * 100);
      document.getElementById('usernameInput').value = rand;
    }

    function loginUser() {
      const val = document.getElementById('usernameInput').value.trim();
      if (!val) return alert('Please enter a username');
      currentUser = val;
      localStorage.setItem('esir_hybrid_user', currentUser);
      showApp();
    }

    function expressGuestLogin() {
      randomizeUsername();
      loginUser();
    }

    function logout() {
      localStorage.removeItem('esir_hybrid_user');
      location.reload();
    }

    function showApp() {
      document.getElementById('authOverlay').classList.add('hidden');
      document.getElementById('appContainer').classList.remove('hidden');
      document.getElementById('settingsUsername').textContent = `User: ${currentUser}`;
      renderChats();
      renderMessages();
      renderStories();
      renderGroups();
      renderCalls();
    }

    function showToast(t) {
      let e = document.getElementById('toast');
      e.textContent = t;
      e.classList.add('show');
      clearTimeout(window.toastTimer);
      window.toastTimer = setTimeout(() => e.classList.remove('show'), 2600);
    }

    function switchView(v) {
      document.querySelectorAll('.view').forEach(x => x.classList.toggle('active', x.id === 'view-' + v));
      document.querySelectorAll('.railbtn').forEach(x => x.classList.toggle('active', x.dataset.view === v));
      let titles = { chats: 'Chats', status: 'Status', calls: 'Calls', communities: 'Groups & Communities', maps: 'Maps', discover: 'Discover', settings: 'Settings' };
      document.getElementById('sideTitle').textContent = titles[v] || v;
      let c = chats.find(x => x.id === activeChat);
      document.getElementById('topTitle').textContent = v === 'chats' ? (c ? c.name : 'ESIR Hub') : titles[v];
      document.getElementById('topSubtitle').textContent = v === 'chats' ? 'Online · Interactive conversation' : 'All-in-one concept platform';
      document.getElementById('topAvatar').textContent = v === 'chats' ? (c ? c.avatar : '👋') : '✦';
    }

    document.querySelectorAll('.railbtn').forEach(b => b.addEventListener('click', () => switchView(b.dataset.view)));

    function renderChats() {
      let q = (document.getElementById('chatSearch')?.value || '').toLowerCase();
      let visible = chats.filter(c => (c.name + ' ' + c.preview).toLowerCase().includes(q) && (filterMode === 'all' || (filterMode === 'unread' ? c.unread > 0 : filterMode === 'groups' ? c.type === 'group' : true)));
      document.getElementById('chatList').innerHTML = visible.map(c => `
        <button class="person ${c.id === activeChat ? 'active' : ''}" onclick="openChat(${c.id})">
          <span class="avatar">${c.avatar}</span>
          <span class="person-copy">
            <span class="person-top"><span>${esc(c.name)}</span><span class="time">${c.time}</span></span>
            <span class="person-preview">${esc(c.preview)}</span>
          </span>
          ${c.unread ? `<span class="unread">${c.unread}</span>` : ''}
        </button>
      `).join('') || '<div class="empty">No chats found.</div>';
    }

    function filterChats(v) { renderChats(); }
    function setFilter(b, m) { filterMode = m; document.querySelectorAll('.filter').forEach(x => x.classList.toggle('active', x === b)); renderChats(); }

    function openChat(id) {
      activeChat = id;
      switchView('chats');
      renderChats();
      renderMessages();
    }

    function openAIChat() {
      openChat(2);
    }

    function renderMessages() {
      let c = chats.find(x => x.id === activeChat);
      if (!c) return;
      document.getElementById('topTitle').textContent = c.name;
      document.getElementById('topAvatar').textContent = c.avatar;
      document.getElementById('messages').innerHTML = '<div class="daytag">TODAY · Live Workspace</div>' + c.messages.map(m => `
        <div class="msg ${m[0] === 'mine' ? 'mine' : ''}">
          ${esc(m[1])}
          <span class="stamp">${m[2]}${m[0] === 'mine' ? ' ✓✓' : ''}</span>
        </div>
      `).join('');
      document.getElementById('messages').scrollTop = 999999;
    }

    document.getElementById('messageForm').addEventListener('submit', e => {
      e.preventDefault();
      let input = document.getElementById('messageInput'), t = input.value.trim();
      if (!t) return;
      let c = chats.find(x => x.id === activeChat);
      const timeStr = new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
      c.messages.push(['mine', t, timeStr]);
      c.preview = t;
      c.time = 'Now';
      input.value = '';
      renderMessages();
      renderChats();

      if (c.type === 'ai') {
        setTimeout(() => {
          c.messages.push(['them', `AI Response: I received "${t}". How can I assist you further?`, new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' })]);
          renderMessages();
        }, 800);
      }
    });

    function newChat() {
      let name = prompt('Name for new chat:');
      if (!name || !name.trim()) return;
      let id = Date.now();
      chats.unshift({ id, name: name.trim(), avatar: '🙂', preview: 'New conversation', time: 'Now', unread: 0, type: 'person', messages: [['them', 'New conversation started.', 'Now']] });
      openChat(id);
    }

    function sendPollPrompt() {
      let q = prompt('Poll Question:');
      if (q) {
        let c = chats.find(x => x.id === activeChat);
        c.messages.push(['mine', `📊 POLL: ${q}`, new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' })]);
        renderMessages();
      }
    }

    function renderStories() {
      let arr = [['＋', 'Your status', 'add'], ['👩🏽', 'Amina', ''], ['🧑🏾', 'Brian', ''], ...customStatuses.map(s => ['🟢', 'You', ''])];
      document.getElementById('storyRow').innerHTML = arr.map((s, i) => `
        <button class="story ${s[2]}" onclick="${i === 0 ? 'document.getElementById(\'statusInput\').focus()' : `showToast('Viewing ${s[1]} status story.')`}">
          <span class="story-ring"><span>${s[0]}</span></span>
          <span>${s[1]}</span>
        </button>
      `).join('');
    }

    document.getElementById('statusForm').addEventListener('submit', e => {
      e.preventDefault();
      let t = document.getElementById('statusInput').value.trim();
      if (!t) return showToast('Write a status first.');
      customStatuses.unshift({ text: t, audience: document.getElementById('statusAudience').value });
      document.getElementById('myStatus').innerHTML = `
        <div class="status-card">
          <strong>Your status · Just now</strong>
          <p class="status-text">${esc(t)}</p>
          <span class="muted small">Audience: ${esc(customStatuses[0].audience)}</span>
        </div>
      `;
      document.getElementById('statusInput').value = '';
      renderStories();
      showToast('Status published!');
    });

    function renderGroups() {
      let defaults = [['🏡', 'Family Group', '8 members'], ['🌳', 'Ruiru Community', '126 members']];
      let all = [...customGroups, ...defaults];
      document.getElementById('groupList').innerHTML = all.map(g => `
        <div class="group-card" style="display:flex;align-items:center;gap:13px">
          <div class="avatar">${g[0]}</div>
          <div style="flex:1"><strong>${esc(g[1])}</strong><div class="muted small">${esc(g[2])}</div></div>
          <button class="btn light" onclick="showToast('Opened group ${esc(g[1])}')">Open</button>
        </div>
      `).join('');
      document.getElementById('communityList').innerHTML = communities.map((c, i) => `
        <div class="community-card" style="display:flex;align-items:center;gap:13px">
          <div class="avatar">${c[0]}</div>
          <div style="flex:1"><strong>${c[1]}</strong><div class="muted small">${c[2]} · ${c[3]}</div></div>
          <button class="btn outline" onclick="joinCommunity(${i},this)">Join</button>
        </div>
      `).join('');
    }

    function createGroup() {
      let name = prompt('Group Name:');
      if (!name || !name.trim()) return;
      customGroups.unshift(['👥', name.trim(), 'New Group · You are Admin']);
      renderGroups();
      showToast('Group created!');
    }

    function joinCommunity(i, b) {
      b.textContent = 'Joined ✓';
      b.classList.remove('outline');
      b.classList.add('light');
      b.disabled = true;
      showToast('Joined community!');
    }

    document.getElementById('mapForm').addEventListener('submit', e => {
      e.preventDefault();
      const q = document.getElementById('mapQuery').value.trim();
      if (!q) return;
      document.getElementById('mapFrame').src = 'https://www.openstreetmap.org/export/embed.html?search=' + encodeURIComponent(q) + '&layer=mapnik';
    });

    function useMyArea() {
      document.getElementById('mapQuery').value = 'Nairobi, Kenya';
      document.getElementById('mapForm').requestSubmit();
    }

    function shareMap() {
      let q = document.getElementById('mapQuery').value.trim() || 'Nairobi, Kenya';
      let c = chats.find(x => x.id === activeChat);
      c.messages.push(['mine', `📍 Map location: https://www.openstreetmap.org/search?query=${encodeURIComponent(q)}`, 'Now']);
      c.preview = '📍 Shared map pin';
      switchView('chats');
      renderChats();
      renderMessages();
      showToast('Map pin shared to chat!');
    }

    function openMapExternal() {
      let q = document.getElementById('mapQuery').value.trim() || 'Nairobi, Kenya';
      window.open('https://www.openstreetmap.org/search?query=' + encodeURIComponent(q), '_blank', 'noopener');
    }

    function renderCalls() {
      document.getElementById('callList').innerHTML = calls.map(c => `
        <div class="call-card">
          <div class="avatar">${c[0]}</div>
          <div class="grow"><strong>${c[1]}</strong><div class="muted small">${c[2]}</div></div>
          <button class="iconbtn" onclick="showToast('Voice call simulated.')">☎</button>
        </div>
      `).join('');
    }

    function esc(s) {
      return String(s).replace(/[&<>"']/g, c => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;' }[c]));
    }

    window.onload = init;
  </script>
</body>
</html>
# Esir-
