---
layout: single
title: "ResearchLens"
permalink: /scholar-scraper/
author_profile: true
---

<style>
.scholar-wrap {
  font-family: inherit;
  font-size: 14px;
  color: inherit;
  max-width: 100%;
  width: 100%;
}

.sch-sub {
  font-size: 12px;
  letter-spacing: 1px;
  color: #888;
  margin-top: 4px;
  margin-bottom: 16px;
}

.sch-card {
  border: 1px solid #ccc;
  background: #fff;
  padding: 16px;
  margin-bottom: 16px;
  border-radius: 3px;
}
.sch-card-label {
  font-size: 10px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: #999;
  margin-bottom: 12px;
}

.sch-search-row { display: flex; gap: 8px; margin-bottom: 10px; }

.sch-input {
  background: #fff;
  border: 1px solid #bbb;
  color: #222;
  font-family: inherit;
  font-size: 13px;
  padding: 8px 11px;
  outline: none;
  transition: border-color 0.2s;
  width: 100%;
  border-radius: 2px;
}
.sch-input:focus { border-color: #555; }
.sch-input::placeholder { color: #aaa; }

.sch-select {
  background: #fff;
  border: 1px solid #bbb;
  color: #222;
  font-family: inherit;
  font-size: 13px;
  padding: 8px 11px;
  outline: none;
  transition: border-color 0.2s;
  width: 100%;
  border-radius: 2px;
}
.sch-select:focus { border-color: #555; }

.sch-btn-search {
  display: flex; align-items: center; gap: 7px;
  background: #333; color: #fff;
  border: none; padding: 8px 20px;
  font-family: inherit; font-weight: 600; font-size: 13px;
  cursor: pointer; transition: background 0.15s;
  white-space: nowrap; flex-shrink: 0; border-radius: 2px;
}
.sch-btn-search:hover { background: #111; }
.sch-btn-search:active { background: #000; }
.sch-btn-search:disabled { opacity: 0.5; cursor: not-allowed; }

.sch-tips {
  display: flex; flex-wrap: wrap; gap: 4px 14px;
  font-size: 11px; color: #aaa; margin-bottom: 14px; line-height: 1.6;
}
.sch-tips .lbl { color: #666; }
.sch-tips .mono { font-family: monospace; color: #555; font-size: 11px; }

.sch-filters { display: grid; grid-template-columns: repeat(2,1fr); gap: 10px; margin-bottom: 14px; }
@media(min-width:600px){ .sch-filters { grid-template-columns: repeat(4,1fr); } }

.sch-field-label {
  font-size: 10px; letter-spacing: 1px; text-transform: uppercase;
  color: #888; display: block; margin-bottom: 5px;
}

.sch-adv-toggle {
  display: flex; align-items: center; gap: 5px;
  background: none; border: none;
  font-family: inherit; font-size: 12px;
  color: #888; cursor: pointer; transition: color 0.2s; padding: 0;
}
.sch-adv-toggle:hover { color: #333; }

.sch-adv-panel { padding-top: 14px; border-top: 1px solid #ddd; margin-top: 14px; }

.sch-toggle-label { display: flex; align-items: center; gap: 10px; cursor: pointer; margin-bottom: 14px; }
.sch-toggle-track {
  position: relative; width: 34px; height: 18px; border-radius: 18px;
  background: #ccc; border: 1px solid #bbb;
  transition: background 0.2s; flex-shrink: 0;
}
.sch-toggle-track.on { background: #333; border-color: #333; }
.sch-toggle-thumb {
  position: absolute; top: 2px; left: 2px;
  width: 12px; height: 12px; border-radius: 50%;
  background: #fff; transition: left 0.2s;
}
.sch-toggle-track.on .sch-toggle-thumb { left: 18px; }
.sch-toggle-text { font-size: 13px; color: #444; }

.sch-survey-btns { display: flex; gap: 6px; margin-bottom: 6px; }
.sch-survey-btn {
  flex: 1; padding: 5px;
  font-family: inherit; font-size: 12px; font-weight: 500;
  border: 1px solid #bbb; background: #f5f5f5; color: #555;
  cursor: pointer; transition: all 0.15s; border-radius: 2px;
}
.sch-survey-btn:hover { border-color: #333; color: #222; }
.sch-survey-btn.active { background: #333; color: #fff; border-color: #333; }

.sch-error {
  display: flex; align-items: flex-start; gap: 10px;
  border: 1px solid #f5c6c6; background: #fff5f5;
  padding: 10px 14px; margin-bottom: 14px;
  color: #c00; font-size: 13px; border-radius: 2px;
}

.sch-loading { border: 1px solid #ddd; background: #fafafa; padding: 50px 20px; text-align: center; margin-bottom: 14px; border-radius: 3px; }
.sch-spin {
  display: inline-block; width: 28px; height: 28px;
  border: 2px solid #ddd; border-top-color: #333;
  border-radius: 50%; animation: schSpin 0.8s linear infinite; margin-bottom: 14px;
}
@keyframes schSpin { to { transform: rotate(360deg); } }
.sch-loading-title { font-size: 13px; color: #555; }
.sch-loading-sub { font-size: 11px; color: #aaa; margin-top: 4px; }

.sch-toolbar {
  display: flex; align-items: center; justify-content: space-between;
  flex-wrap: wrap; gap: 10px; margin-bottom: 12px;
}
.sch-toolbar-title {
  font-size: 16px; font-weight: 600;
  display: flex; align-items: center; gap: 8px; color: #222;
}
.sch-slash { color: #999; font-size: 12px; }
.sch-meta { font-size: 11px; color: #999; font-weight: 400; }
.sch-toolbar-actions { display: flex; align-items: center; gap: 8px; flex-wrap: wrap; }
.sch-sel-info { font-size: 11px; }
.sch-sel-active { color: #555; font-weight: 600; }
.sch-sel-dim { color: #aaa; }

.sch-btn-export {
  display: inline-flex; align-items: center; gap: 5px;
  border: 1px solid #bbb; background: #fff; color: #555;
  font-family: inherit; font-size: 12px;
  padding: 5px 12px; cursor: pointer; transition: border-color 0.2s, color 0.2s;
  border-radius: 2px;
}
.sch-btn-export:hover { border-color: #333; color: #222; }
.sch-btn-export:disabled { opacity: 0.4; cursor: not-allowed; }

.sch-table-wrap { border: 1px solid #ccc; background: #fff; overflow: hidden; border-radius: 3px; }
.sch-table-scroll { overflow-x: auto; }
table.sch-table { width: 100%; border-collapse: collapse; table-layout: fixed; font-size: 12px; }
table.sch-table thead tr { border-bottom: 1px solid #ccc; background: #f5f5f5; }
table.sch-table th {
  padding: 9px 10px;
  font-family: inherit; font-size: 10px; letter-spacing: 1px;
  text-transform: uppercase; color: #888; text-align: left; font-weight: 600;
}
table.sch-table th.r { text-align: right; }
table.sch-table th.c { text-align: center; }
table.sch-table tbody tr { border-bottom: 1px solid #eee; transition: background 0.1s; }
table.sch-table tbody tr:hover { background: #fafafa; }
table.sch-table tbody tr.sch-sel { background: #f0f0f0; }
table.sch-table tbody tr:last-child { border-bottom: none; }
table.sch-table td { padding: 9px 10px; vertical-align: top; color: #222; }
table.sch-table td.r { text-align: right; }
table.sch-table td.c { text-align: center; }

.sch-td-title { font-weight: 500; text-align: left; color: #222; line-height: 1.4; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
.sch-td-sec { color: #666; line-height: 1.5; }
.sch-year { font-size: 11px; text-align: center; font-weight: 500; color: #555;  }
.sch-cite { font-size: 11px; text-align: left; font-weight: 500; color: #555; }
.sch-dash { color: #ccc; }
.sch-btn-icon {
  display: inline-flex; align-items: center; justify-content: center;
  width: 26px; height: 26px;
  background: none; border: none; color: #aaa; cursor: pointer; transition: color 0.15s; font-size: 13px;
}
.sch-btn-icon:hover { color: #333; }
a.sch-btn-icon { text-decoration: none; }

.sch-abs-row td { padding-top: 0 !important; }
.sch-abs-inner { border-left: 2px solid #ddd; padding-left: 12px; margin-left: 18px; }
.sch-abs-text { font-size: 11px; color: #555; line-height: 1.65; }

.sch-cards { display: flex; flex-direction: column; gap: 10px; }
.sch-card-item { border: 1px solid #ccc; background: #fff; transition: border-color 0.2s; border-radius: 3px; }
.sch-card-item.sch-sel { border-color: #666; background: #fafafa; }
.sch-card-hd { display: flex; align-items: flex-start; gap: 8px; padding: 12px 12px 9px; border-bottom: 1px solid #eee; cursor: pointer; }
.sch-card-title { font-weight: 500; font-size: 13px; line-height: 1.4; flex: 1; color: #222; }
.sch-card-bd { padding: 9px 12px; }
.sch-card-meta { display: flex; flex-wrap: wrap; align-items: center; gap: 6px; margin-bottom: 6px; border-top: 1px solid #eee; padding-top: 8px; }
.sch-card-pub { display: flex; justify-content: space-between; font-size: 11px; color: #666; }

.sch-empty { border: 1px solid #ddd; background: #fafafa; padding: 50px 20px; text-align: center; border-radius: 3px; }
.sch-empty-icon { font-size: 28px; margin-bottom: 10px; opacity: 0.3; }
.sch-empty-text { font-size: 13px; color: #888; }

.sch-footer { text-align: center; font-size: 11px; color: #aaa; line-height: 2; margin-top: 32px; }
.sch-footer a { color: #555; text-decoration: underline; }
.sch-footer a:hover { color: #222; }

.sch-spinner-sm { display: inline-block; width: 12px; height: 12px; border: 2px solid #ccc; border-top-color: #333; border-radius: 50%; animation: schSpin 0.7s linear infinite; }

.sch-desktop { display: none; }
.sch-mobile { display: block; }
@media(min-width:640px){ .sch-desktop { display: block; } .sch-mobile { display: none; } }

input[type="checkbox"] { width: 13px; height: 13px; cursor: pointer; flex-shrink: 0; }
</style>

<div class="scholar-wrap">

  <p class="sch-sub">A tool for scraping academic articles to support literature reviews · Powered by <a href="https://openalex.org" target="_blank" rel="noopener noreferrer">OpenAlex</a></p>

  <!-- SEARCH FORM -->
  <div class="sch-card">
    <p class="sch-card-label">// Search</p>

    <div class="sch-search-row">
      <input class="sch-input" type="text" id="sch-query" placeholder="e.g. deep learning image classification, transformer attention..." />
      <button class="sch-btn-search" id="sch-search-btn" onclick="schDoSearch()">
        <span id="sch-search-icon">⌕</span>
        <span id="sch-search-label">Search</span>
      </button>
    </div>

    <div class="sch-tips">
      <span><span class="lbl">Multiple terms:</span> type freely — <span class="mono">federated learning energy</span></span>
      <span style="color:#ddd">·</span>
      <span><span class="lbl">Exact phrase:</span> use quotes — <span class="mono">"federated learning"</span></span>
      <span style="color:#ddd">·</span>
      <span>AND / OR / NOT not supported</span>
    </div>

    <div class="sch-filters">
      <div>
        <label class="sch-field-label">From year</label>
        <input class="sch-input" type="number" id="sch-year-from" placeholder="2018" />
      </div>
      <div>
        <label class="sch-field-label">To year</label>
        <input class="sch-input" type="number" id="sch-year-to" placeholder="2026" />
      </div>
      <div>
        <label class="sch-field-label">Results</label>
        <select class="sch-select" id="sch-num">
          <option value="10">10 papers</option>
          <option value="20" selected>20 papers</option>
          <option value="50">50 papers</option>
          <option value="100">100 papers</option>
        </select>
      </div>
      <div>
        <label class="sch-field-label">Sort by</label>
        <select class="sch-select" id="sch-sort">
          <option value="relevance_score">Most relevant</option>
          <option value="cited_by_count">Most cited</option>
          <option value="publication_date">Most recent</option>
        </select>
      </div>
    </div>

    <button class="sch-adv-toggle" onclick="schToggleAdv()">
      <span id="sch-adv-chev">▾</span>
      <span id="sch-adv-lbl">Advanced options</span>
    </button>

    <div class="sch-adv-panel" id="sch-adv-panel" style="display:none;">
      <label class="sch-toggle-label" onclick="schToggleOA()">
        <div class="sch-toggle-track" id="sch-oa-track">
          <div class="sch-toggle-thumb"></div>
        </div>
        <span class="sch-toggle-text">Only show Open Access papers (free to read)</span>
      </label>
      <div>
        <p class="sch-field-label" style="margin-bottom:8px;">Survey &amp; Review papers</p>
        <div class="sch-survey-btns">
          <button class="sch-survey-btn active" data-val="all" onclick="schSetSurvey(this)">All</button>
          <button class="sch-survey-btn" data-val="exclude" onclick="schSetSurvey(this)">Exclude</button>
          <button class="sch-survey-btn" data-val="only" onclick="schSetSurvey(this)">Only</button>
        </div>
        <p style="font-size:11px;color:#aaa;">Filters by title keywords: survey, review, meta-analysis, overview...</p>
      </div>
    </div>
  </div>

  <!-- ERROR -->
  <div class="sch-error" id="sch-error" style="display:none;">
    <span>⚠</span><span id="sch-error-msg"></span>
  </div>

  <!-- LOADING -->
  <div class="sch-loading" id="sch-loading" style="display:none;">
    <div class="sch-spin"></div>
    <p class="sch-loading-title">Searching for papers...</p>
    <p class="sch-loading-sub">Querying OpenAlex — world's largest open academic catalog</p>
  </div>

  <!-- RESULTS -->
  <div id="sch-results" style="display:none;">
    <div class="sch-toolbar">
      <div class="sch-toolbar-title">
        <span class="sch-slash">//</span> Results
        <span class="sch-meta" id="sch-results-meta"></span>
      </div>
      <div class="sch-toolbar-actions">
        <span class="sch-sel-info sch-sel-dim" id="sch-sel-info">None selected — export all</span>
        <button class="sch-btn-export" id="sch-btn-csv" onclick="schExportCSV()">↓ <span id="sch-csv-lbl">CSV</span></button>
      </div>
    </div>

    <div class="sch-empty" id="sch-empty" style="display:none;">
      <div class="sch-empty-icon">✕</div>
      <p class="sch-empty-text">No papers found. Try different keywords or adjust the filters.</p>
    </div>

    <!-- Desktop table -->
    <div class="sch-table-wrap sch-desktop" id="sch-table-wrap">
      <div class="sch-table-scroll">
        <table class="sch-table">
          <thead>
            <tr>
              <th style="width:4%"><input type="checkbox" id="sch-cb-all" onchange="schToggleSelectAll()" /></th>
              <th style="width:33%">Title</th>
              <th style="width:17%">Authors</th>
              <th style="width:6%">Year</th>
              <th style="width:20%">Published in</th>
              <th class="r" style="width:7%">Cite</th>
              <th class="c" style="width:5%">OA</th>
              <th class="c" style="width:5%">Abs</th>
              <th class="c" style="width:5%">URL</th>
            </tr>
          </thead>
          <tbody id="sch-tbody"></tbody>
        </table>
      </div>
    </div>

    <!-- Mobile cards -->
    <div class="sch-cards sch-mobile" id="sch-cards"></div>
  </div>

</div>

<script>
(function(){
  var articles=[], selectedIds=new Set(), expandedIds=new Set();
  var lastQuery='', totalResults=0, isLoading=false;
  var openAccessOnly=false, surveyFilter='all', advOpen=false;

  function g(id){ return document.getElementById(id); }
  function show(id){ var e=g(id); if(e) e.style.display=''; }
  function hide(id){ var e=g(id); if(e) e.style.display='none'; }
  function esc(s){ return String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;'); }

  window.schToggleAdv = function(){
    advOpen=!advOpen;
    g('sch-adv-panel').style.display=advOpen?'':'none';
    g('sch-adv-chev').textContent=advOpen?'▴':'▾';
    g('sch-adv-lbl').textContent=advOpen?'Hide advanced':'Advanced options';
  };

  window.schToggleOA = function(){
    openAccessOnly=!openAccessOnly;
    g('sch-oa-track').classList.toggle('on',openAccessOnly);
  };

  window.schSetSurvey = function(btn){
    document.querySelectorAll('.sch-survey-btn').forEach(function(b){ b.classList.remove('active'); });
    btn.classList.add('active');
    surveyFilter=btn.dataset.val;
  };

  function decodeAbstract(inv){
    if(!inv) return '';
    var entries=Object.entries(inv);
    if(!entries.length) return '';
    var max=0;
    entries.forEach(function(e){ e[1].forEach(function(p){ if(p>max) max=p; }); });
    var words=new Array(max+1);
    entries.forEach(function(e){ e[1].forEach(function(p){ words[p]=e[0]; }); });
    return words.filter(Boolean).join(' ');
  }

  function fmtAuthors(au){
    if(!au||!au.length) return '';
    var names=au.slice(0,4).map(function(a){ return a.author&&a.author.display_name||''; });
    return names.join(', ')+(au.length>4?' +'+(au.length-4):'');
  }

  window.schDoSearch = async function(){
    var query=g('sch-query').value.trim();
    if(!query){ schShowErr('Please enter a search keyword.'); return; }
    if(isLoading) return;
    isLoading=true; schHideErr();
    hide('sch-results'); hide('sch-loading');
    articles=[]; selectedIds=new Set(); expandedIds=new Set(); lastQuery=query;
    var btn=g('sch-search-btn');
    g('sch-search-icon').innerHTML='<span class="sch-spinner-sm"></span>';
    g('sch-search-label').textContent='Searching...';
    btn.disabled=true;
    show('sch-loading');
    try {
      var params=new URLSearchParams({search:query,per_page:g('sch-num').value,mailto:'scholar@huongdm1896.github.io'});
      var filters=['type:article|preprint|proceedings-article','language:en'];
      var yf=g('sch-year-from').value, yt=g('sch-year-to').value;
      if(yf&&yt) filters.push('publication_year:'+yf+'-'+yt);
      else if(yf) filters.push('publication_year:>'+(Number(yf)-1));
      else if(yt) filters.push('publication_year:<'+(Number(yt)+1));
      if(openAccessOnly) filters.push('open_access.is_oa:true');
      params.set('filter',filters.join(','));
      var srt=g('sch-sort').value;
      if(srt!=='relevance_score') params.set('sort',srt+':desc');
      params.set('select','title,authorships,publication_year,primary_location,cited_by_count,abstract_inverted_index,doi,open_access');
      var resp=await fetch('https://api.openalex.org/works?'+params.toString());
      if(!resp.ok) throw new Error('API error: '+resp.status);
      var data=await resp.json();
      totalResults=data.meta&&data.meta.count||0;
      var SR=/\b(survey|review|systematic review|literature review|meta.analysis|overview|state of the art)\b/i;
      var mapped=(data.results||[]).map(function(w){
        return {
          title:w.title||'(No title)',
          authors:fmtAuthors(w.authorships),
          year:String(w.publication_year||''),
          publication:(w.primary_location&&w.primary_location.source&&w.primary_location.source.display_name)||'',
          citations:w.cited_by_count||0,
          abstract:decodeAbstract(w.abstract_inverted_index),
          link:w.doi?'https://doi.org/'+w.doi.replace('https://doi.org/',''):'',
          openAccess:!!(w.open_access&&w.open_access.is_oa)
        };
      });
      articles=mapped.filter(function(a){
        var is=SR.test(a.title);
        if(surveyFilter==='exclude') return !is;
        if(surveyFilter==='only') return is;
        return true;
      });
      schRenderResults();
    } catch(e){
      schShowErr(e.message||'Unknown error.');
    } finally {
      isLoading=false; hide('sch-loading');
      g('sch-search-icon').textContent='⌕';
      g('sch-search-label').textContent='Search';
      btn.disabled=false;
    }
  };

  function schRenderResults(){
    show('sch-results');
    g('sch-results-meta').textContent=articles.length+' / '+totalResults.toLocaleString()+' papers — "'+lastQuery+'"';
    if(!articles.length){ show('sch-empty'); hide('sch-table-wrap'); g('sch-cards').innerHTML=''; return; }
    hide('sch-empty');
    schRenderTable(); schRenderCards(); schUpdateSelInfo();
  }

  function schRenderTable(){
    var tb=g('sch-tbody'); tb.innerHTML='';
    articles.forEach(function(a,i){
      var tr=document.createElement('tr');
      tr.id='sch-row-'+i;
      if(selectedIds.has(i)) tr.classList.add('sch-sel');
      tr.innerHTML=
        '<td><input type="checkbox"'+(selectedIds.has(i)?' checked':'')+' onchange="schToggleSel('+i+')" /></td>'+
        '<td><div class="sch-td-title">'+esc(a.title)+'</div></td>'+
        '<td class="sch-td-sec">'+esc(a.authors)+'</td>'+
        '<td><span class="sch-year">'+esc(a.year)+'</span></td>'+
        '<td class="sch-td-sec">'+esc(a.publication)+'</td>'+
        '<td class="r">'+(a.citations?'<span class="sch-cite">'+a.citations.toLocaleString()+'</span>':'<span class="sch-dash">—</span>')+'</td>'+
        '<td class="c">'+(a.openAccess?'<span style="color:#2a9d2a;font-size:13px;" title="Open Access">🔓</span>':'<span class="sch-dash">—</span>')+'</td>'+
        '<td class="c">'+(a.abstract?'<button class="sch-btn-icon" id="sch-abs-btn-'+i+'" onclick="schToggleExp('+i+')" title="Show abstract">▾</button>':'<span class="sch-dash">—</span>')+'</td>'+
        '<td class="c">'+(a.link?'<a class="sch-btn-icon" href="'+esc(a.link)+'" target="_blank" rel="noopener noreferrer" title="Open paper">↗</a>':'<span class="sch-dash">—</span>')+'</td>';
      tb.appendChild(tr);
      if(a.abstract){
        var absTr=document.createElement('tr');
        absTr.className='sch-abs-row'; absTr.id='sch-abs-row-'+i;
        absTr.style.display=expandedIds.has(i)?'':'none';
        absTr.innerHTML='<td colspan="9"><div class="sch-abs-inner"><p class="sch-abs-text">'+esc(a.abstract)+'</p></div></td>';
        tb.appendChild(absTr);
      }
    });
  }

  function schRenderCards(){
    var list=g('sch-cards'); list.innerHTML='';
    articles.forEach(function(a,i){
      var div=document.createElement('div');
      div.className='sch-card-item'+(selectedIds.has(i)?' sch-sel':'');
      div.id='sch-card-'+i;
      var absExpanded=expandedIds.has(i);
      div.innerHTML=
        '<div class="sch-card-hd" onclick="schToggleSel('+i+')">'+
          '<input type="checkbox"'+(selectedIds.has(i)?' checked':'')+' onclick="event.stopPropagation()" onchange="schToggleSel('+i+')" />'+
          '<span class="sch-card-title">'+esc(a.title)+'</span>'+
          (a.link?'<a href="'+esc(a.link)+'" target="_blank" rel="noopener noreferrer" class="sch-btn-icon" onclick="event.stopPropagation()" title="Open paper">↗</a>':'')+
        '</div>'+
        '<div class="sch-card-bd">'+
          (a.abstract?
            '<div style="margin-bottom:8px;">'+
              '<button class="sch-adv-toggle" onclick="schToggleExp('+i+')" id="sch-card-abs-btn-'+i+'">'+
                '<span>'+(absExpanded?'▴':'▾')+'</span> Abstract'+
              '</button>'+
              '<p class="sch-abs-text" id="sch-card-abs-text-'+i+'" style="'+(absExpanded?'':'display:none;')+'margin-top:6px;border-left:2px solid #ddd;padding-left:8px;">'+esc(a.abstract)+'</p>'+
            '</div>':'')+''+
          '<div class="sch-card-meta">'+
            '<span class="sch-year">'+esc(a.year)+'</span>'+
            (a.openAccess?'<span style="font-size:11px;color:#2a9d2a;">🔓 Open Access</span>':'')+
            '<span style="font-size:11px;color:#666;">'+esc(a.authors)+'</span>'+
          '</div>'+
          '<div class="sch-card-pub"><span>'+esc(a.publication)+'</span>'+(a.citations?'<span style="font-size:11px;color:#aaa;">❝ '+a.citations.toLocaleString()+'</span>':'')+'</div>'+
        '</div>';
      list.appendChild(div);
    });
  }

  window.schToggleSel = function(i){
    if(selectedIds.has(i)) selectedIds.delete(i); else selectedIds.add(i);
    schUpdateRow(i); schUpdateSelectAllCb(); schUpdateSelInfo(); schUpdateExportLbls();
  };

  window.schToggleSelectAll = function(){
    var cb=g('sch-cb-all');
    if(cb.checked) articles.forEach(function(_,i){ selectedIds.add(i); });
    else selectedIds.clear();
    articles.forEach(function(_,i){ schUpdateRow(i); });
    schUpdateSelInfo(); schUpdateExportLbls();
  };

  function schUpdateRow(i){
    var row=g('sch-row-'+i), card=g('sch-card-'+i);
    if(row){ row.classList.toggle('sch-sel',selectedIds.has(i)); var cb=row.querySelector('input[type=checkbox]'); if(cb) cb.checked=selectedIds.has(i); }
    if(card){ card.classList.toggle('sch-sel',selectedIds.has(i)); var cb2=card.querySelector('input[type=checkbox]'); if(cb2) cb2.checked=selectedIds.has(i); }
  }

  function schUpdateSelectAllCb(){
    var cb=g('sch-cb-all'); if(!cb) return;
    cb.checked=selectedIds.size===articles.length&&articles.length>0;
    cb.indeterminate=selectedIds.size>0&&selectedIds.size<articles.length;
  }

  function schUpdateSelInfo(){
    var n=selectedIds.size, si=g('sch-sel-info');
    if(n>0){ si.className='sch-sel-info sch-sel-active'; si.textContent=n+' paper'+(n>1?'s':'')+' selected'; }
    else { si.className='sch-sel-info sch-sel-dim'; si.textContent='None selected — export all'; }
  }

  function schUpdateExportLbls(){
    var n=selectedIds.size;
    g('sch-csv-lbl').textContent=n>0?'CSV ('+n+')':'CSV';
  }

  window.schToggleExp = function(i){
    if(expandedIds.has(i)) expandedIds.delete(i); else expandedIds.add(i);
    var absRow=g('sch-abs-row-'+i), absBtn=g('sch-abs-btn-'+i);
    if(absRow) absRow.style.display=expandedIds.has(i)?'':'none';
    if(absBtn){ absBtn.textContent=expandedIds.has(i)?'▴':'▾'; absBtn.title=expandedIds.has(i)?'Hide abstract':'Show abstract'; }
    var cardBtn=g('sch-card-abs-btn-'+i), cardTxt=g('sch-card-abs-text-'+i);
    if(cardBtn){ var sp=cardBtn.querySelector('span'); if(sp) sp.textContent=expandedIds.has(i)?'▴':'▾'; }
    if(cardTxt) cardTxt.style.display=expandedIds.has(i)?'':'none';
  };

  function schShowErr(msg){ g('sch-error-msg').textContent=msg; show('sch-error'); }
  function schHideErr(){ hide('sch-error'); }

  function schGetTarget(){ return selectedIds.size>0?articles.filter(function(_,i){ return selectedIds.has(i); }):articles; }

  window.schExportCSV = function(){
    var t=schGetTarget(); if(!t.length) return;
    var h=['Title','Authors','Year','Published in','Citations','Abstract','DOI/Link','Open Access'];
    var rows=t.map(function(a){ return [a.title,a.authors,a.year,a.publication,a.citations,a.abstract,a.link,a.openAccess?'Yes':'No']; });
    var csv=[h].concat(rows).map(function(r){ return r.map(function(c){ return '"'+String(c||'').replace(/"/g,'""')+'"'; }).join(','); }).join('\n');
    schDl('\uFEFF'+csv,'scholar_'+lastQuery.slice(0,30)+'.csv','text/csv;charset=utf-8;');
  };

  function schDl(content,filename,type){
    var blob=new Blob([content],{type:type});
    var a=document.createElement('a');
    a.href=URL.createObjectURL(blob); a.download=filename; a.click();
    URL.revokeObjectURL(a.href);
  }

  g('sch-query').addEventListener('keydown',function(e){ if(e.key==='Enter') schDoSearch(); });
})();
</script>
