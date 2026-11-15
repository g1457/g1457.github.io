# g1457.github.io

<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="robots" content="noindex">
<title>Miro Hair Kundenformular (Prototyp)</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Space+Grotesk:wght@500;600&display=swap">
<style>
*{box-sizing:border-box}
html,body{margin:0;height:100%}
body{background:#F3F4F2;color:#1C1F1E;font-family:Inter,system-ui,sans-serif;font-size:17px;line-height:1.45;-webkit-text-size-adjust:100%}
button,input{font-family:inherit}
button{cursor:pointer}
button:focus-visible,input:focus-visible{outline:3px solid #1C1F1E;outline-offset:2px}
h1{margin:0;font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:34px;line-height:1.15}
p{margin:8px 0 0 0}
.muted{color:#4F5753}
.small{font-size:15px}
.app{max-width:1024px;min-height:100%;margin:0 auto;display:flex;flex-direction:column}
.top{height:64px;flex-shrink:0;padding:0 40px;display:flex;align-items:center;justify-content:space-between;gap:12px;background:#fff;border-bottom:1px solid #DDE0DC}
.brand{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:18px;letter-spacing:.14em}
.mode{height:32px;padding:0 14px;display:flex;align-items:center;border-radius:16px;font-size:14px;font-weight:600;white-space:nowrap}
.prog{padding:20px 40px 0;display:flex;align-items:center;gap:16px}
.prog .lbl{font-size:14px;font-weight:600;color:#4F5753;width:110px;flex-shrink:0}
.bar{flex-grow:1;height:6px;border-radius:3px;background:#DDE0DC;overflow:hidden}
.bar div{height:6px;border-radius:3px}
.main{flex-grow:1;padding:28px 40px 0;display:flex;flex-direction:column}
.col{display:flex;flex-direction:column}
.row{display:flex;align-items:center}
.card{background:#fff;border:1px solid #DDE0DC;border-radius:14px}
.btn{min-height:54px;padding:0 28px;border-radius:27px;font-size:17px;font-weight:600;border:none;color:#fff}
.btn.ghost{background:transparent;border:1.5px solid #1C1F1E;color:#1C1F1E}
.chip{min-height:50px;padding:0 22px;border-radius:25px;font-size:17px;font-weight:500}
.chip.sm{min-height:44px;padding:0 16px;font-size:15px}
.field{width:100%;height:56px;padding:0 20px;border:1.5px solid #8A918C;border-radius:14px;background:#fff;color:#1C1F1E;font-size:17px}
.item{min-height:80px;padding:14px 24px;display:flex;align-items:center;gap:24px;text-align:left;background:#fff;border:1px solid #DDE0DC;border-radius:14px;font-size:17px;color:#1C1F1E;width:100%}
.time{width:64px;flex-shrink:0;font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:20px}
.tag{height:30px;flex-shrink:0;padding:0 12px;display:flex;align-items:center;border-radius:15px;font-size:14px;font-weight:600}
.kv{display:flex;gap:14px;padding:12px 0;border-bottom:1px solid #ECEEEB}
.kv .k{width:150px;flex-shrink:0;color:#4F5753;font-size:15px}
.kv .v{font-weight:500}
.sign{min-height:104px;padding:12px 24px;display:flex;align-items:center;flex-wrap:wrap;gap:20px;text-align:left;background:#fff;border-radius:14px;font-size:17px;color:#1C1F1E;width:100%}
.center{flex-grow:1;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:20px;text-align:center;padding:40px 0}
.dot{width:72px;height:72px;border-radius:36px;display:flex;align-items:center;justify-content:center}
.nav{flex-shrink:0;padding:24px 40px 28px;display:flex;align-items:center;justify-content:space-between;gap:12px}
.big{font-family:'Space Grotesk',sans-serif;font-weight:600;font-size:34px}
.two{display:flex;gap:24px;flex-wrap:wrap}
.two>div{flex:1 1 380px;min-width:0}
@media (max-width:640px){
 body{font-size:16px}
 h1{font-size:26px}
 .top{padding:0 18px}.prog{padding:16px 18px 0}.main{padding:20px 18px 0}.nav{padding:20px 18px 24px}
 .item{gap:14px;padding:12px 16px;flex-wrap:wrap}.time{width:52px;font-size:18px}
 .kv .k{width:110px}
 .hide-s{display:none}
 .stack-s{flex-direction:column;align-items:stretch !important}
 .btn{padding:0 22px}
}
</style>
</head>
<body>
<div id="app" class="app"></div>
<script>
(function () {
  var ACCENT = '#0F5B57';
  function DCLogic() {}
  DCLogic.prototype.setState = function (p) { this.state = Object.assign({}, this.state || {}, p); paint(); };
  var Component = (function (DCLogic) {

class Component extends DCLogic {
  renderVals() {
    var self = this;
    var accent = this.props.accent || '#0F5B57';
    var st = this.state || {};
    var step = st.step || 0;
    var a = st.a || {};
    var c = st.c || {};
    var set = function (patch) { self.setState(patch); };

    var CATALOG = {
      bb: { label: 'Basic Balayage', dur: '4 Std.', min: 250, max: 320 },
      pb: { label: 'Premium Balayage', dur: '4 Std.', min: 270, max: 350 },
      bl: { label: 'Babylights', dur: '4 Std.', min: 180, max: 240 },
      an: { label: 'Ansatzfarbe-Paket', dur: '2 Std.', min: 100, max: 130 }
    };
    var CUSTOMERS = [
      { id: 'c1', time: '10:30', svc: 'bb', name: 'Lena Hartmann', first: 'Frau Hartmann', tag: 'Erstbesuch', phone: '0151 0000 0001', mail: 'lena.hartmann@example.com' },
      { id: 'c2', time: '12:00', svc: 'an', name: 'Mara Kowalski', first: 'Frau Kowalski', tag: 'Stammkundin', phone: '0151 0000 0002', mail: 'mara.kowalski@example.com' },
      { id: 'c3', time: '14:00', svc: 'pb', name: 'Jule Petersen', first: 'Frau Petersen', tag: 'Erstbesuch', phone: '0151 0000 0003', mail: 'jule.petersen@example.com' },
      { id: 'c4', time: '', svc: '', name: 'Selin Arslan', first: 'Frau Arslan', tag: 'Stammkundin', phone: '0151 0000 0004', mail: 'selin.arslan@example.com' },
      { id: 'c5', time: '', svc: '', name: 'Greta Lindqvist', first: 'Frau Lindqvist', tag: 'Stammkundin', phone: '0151 0000 0005', mail: 'greta.lindqvist@example.com' }
    ];
    var cust = CUSTOMERS[0];
    CUSTOMERS.forEach(function (x) { if (x.id === st.cust) cust = x; });
    if (st.cust === 'new') {
      var nn = (st.newName || '').trim() || 'Neue Kundin';
      cust = { id: 'new', time: '', svc: '', name: nn, first: nn, tag: 'Erstbesuch', phone: (st.newPhone || '').trim() || 'Nicht angegeben', mail: 'Nicht angegeben' };
    }
    var svcId = st.svc || '';
    var svc = CATALOG[svcId] || null;
    var price = st.price || (svc ? svc.min : 0);
    var q = st.q || '';
    var loaded = !!st.loaded;

    var RET_A = { last: 'Vor 1 bis 3 Monaten', home: 'Nein', blond: 'Ja', spray: 'Nein', keratin: 'Nein', henna: 'Nein', allergy: 'Nein', loss: 'Nein', meds: 'Nein' };
    var RET_C = { data: true, health: true, photoDoc: true, photoSocial: false };
    var begin = function (x) {
      var first = x.tag === 'Erstbesuch';
      var s0 = CATALOG[x.svc] || null;
      set({ cust: x.id, ret: !first, step: 1, q: '', svc: x.svc || '', price: s0 ? s0.min : 0,
        a: first ? {} : RET_A, c: first ? {} : RET_C, sig1: !first, sig2: false });
    };
    var needle = q.trim().toLowerCase();
    var shown = [];
    if (needle) shown = CUSTOMERS.filter(function (x) { return x.name.toLowerCase().indexOf(needle) >= 0 || x.phone.replace(/ /g, '').indexOf(needle.replace(/ /g, '')) >= 0; });
    else if (loaded) shown = CUSTOMERS.filter(function (x) { return !!x.time; });
    var customers = shown.map(function (x) {
      var first = x.tag === 'Erstbesuch';
      var s0 = CATALOG[x.svc] || null;
      return {
        time: x.time || '–', name: x.name, tag: x.tag,
        sub: s0 ? (s0.label + ' · ' + s0.dur + ' · ' + s0.min + ' bis ' + s0.max + ' €') : 'Heute ohne Termin in der Liste · letzter Besuch 20.10.2026',
        tagBg: first ? '#FFF1DC' : '#E6ECEA', tagFg: first ? '#7A3E00' : '#1C1F1E',
        pick: function () { begin(x); }
      };
    });
    var svcOpts = Object.keys(CATALOG).map(function (id) {
      var on = id === svcId;
      return { label: CATALOG[id].label, on: on,
        bg: on ? accent : '#FFFFFF', fg: on ? '#FFFFFF' : '#1C1F1E', bd: on ? accent : '#B9BFBA',
        pick: function () { set({ svc: id, price: CATALOG[id].min }); } };
    });

    var PAGES = {
      2: { title: 'Ihre Haarfarbe bisher', hint: 'Damit wir wissen, was schon im Haar ist.', qs: [
        { id: 'last', label: 'Wann wurden Ihre Haare zuletzt gefärbt oder blondiert?', opts: ['Noch nie', 'Vor weniger als 4 Wochen', 'Vor 1 bis 3 Monaten', 'Länger her'] },
        { id: 'home', label: 'Haben Sie zuhause selbst gefärbt?', opts: ['Ja', 'Nein'] },
        { id: 'blond', label: 'Gab es bereits Blondierungen, Tönungen oder Farbentfernungen?', opts: ['Ja', 'Nein'] }
      ] },
      3: { title: 'Besondere Behandlungen', hint: 'Diese drei Dinge verändern, wie Farbe auf dem Haar reagiert.', qs: [
        { id: 'spray', label: 'Haben Sie Ihre Haare mit einem Aufheller-Spray aufgehellt?', opts: ['Ja', 'Nein'] },
        { id: 'keratin', label: 'Gab es eine Keratin-Glättung oder Ähnliches?', opts: ['Ja', 'Nein'] },
        { id: 'henna', label: 'Haben Sie mit Henna oder anderen Pflanzenfarben gefärbt?', opts: ['Ja', 'Nein'] }
      ] },
      4: { title: 'Gesundheit', hint: 'Diese Angaben sind freiwillig. Sie helfen uns, sicher zu arbeiten.', qs: [
        { id: 'allergy', label: 'Gibt es Unverträglichkeiten oder allergische Reaktionen?', opts: ['Ja', 'Nein', 'Keine Angabe'] },
        { id: 'loss', label: 'Leiden Sie aktuell unter Haarbruch oder Haarausfall?', opts: ['Ja', 'Nein', 'Keine Angabe'] },
        { id: 'meds', label: 'Nehmen Sie Medikamente oder gibt es gesundheitliche Besonderheiten?', opts: ['Ja', 'Nein', 'Keine Angabe'] }
      ] },
      5: { title: 'Ihr Wunsch für heute', hint: 'Bei den ersten beiden Fragen können Sie mehreres antippen.', qs: [
        { id: 'goal', multi: true, label: 'Was ist Ihr Wunschziel?', opts: ['Heller', 'Dunkler', 'Natürlicher', 'Auffälliger', 'Grau abdecken', 'Mehr Glanz'] },
        { id: 'nogo', multi: true, label: 'Was darf auf keinen Fall passieren?', opts: ['Zu viel Länge ab', 'Gelbstich', 'Zu dunkel', 'Zu hell', 'Sichtbarer Ansatz'] },
        { id: 'time', label: 'Wie viel Zeit haben Sie heute?', opts: ['Bis 2 Stunden', 'Bis 4 Stunden', 'Offen'] },
        { id: 'budget', label: 'Welches Budget haben Sie eingeplant?', opts: ['Bis 150 €', 'Bis 250 €', 'Bis 350 €', 'Offen'] }
      ] },
      11: { title: 'Kurz-Check', hint: 'Ihr letzter Besuch war am 20.10.2026. Wenn sich nichts geändert hat, übernehmen wir Ihre Angaben von damals.', qs: [
        { id: 'chHair', label: 'Haben Sie seit Ihrem letzten Besuch etwas an Ihren Haaren verändert, zum Beispiel gefärbt, getönt, aufgehellt oder geglättet?', opts: ['Nein, nichts', 'Ja'] },
        { id: 'chHealth', label: 'Hat sich bei Unverträglichkeiten, Medikamenten oder Ihrer Gesundheit etwas geändert?', opts: ['Nein, nichts', 'Ja'] }
      ] }
    };
    var ret = !!st.ret;
    var flow = [1, 2, 3, 4, 5, 6];
    if (ret) {
      flow = [1, 11];
      if (a.chHair === 'Ja') { flow.push(2); flow.push(3); }
      if (a.chHealth === 'Ja') flow.push(4);
      flow.push(5);
    }
    var idx = flow.indexOf(step);
    var isLast = idx === flow.length - 1;
    var page = PAGES[step] || PAGES[2];
    var pageQs = page.qs;
    if (ret && step === 2) pageQs = pageQs.map(function (q) {
      if (q.id !== 'last') return q;
      return { id: q.id, label: q.label, opts: q.opts.filter(function (o) { return o !== 'Noch nie'; }) };
    });
    var questions = pageQs.map(function (q) {
      var cur = a[q.id];
      return {
        label: q.label,
        opts: q.opts.map(function (label) {
          var on = q.multi ? (cur || []).indexOf(label) >= 0 : cur === label;
          return {
            label: label, on: on,
            bg: on ? accent : '#FFFFFF', fg: on ? '#FFFFFF' : '#1C1F1E', bd: on ? accent : '#B9BFBA',
            pick: function () {
              var next = Object.assign({}, a);
              if (q.multi) {
                var arr = (cur || []).slice();
                var i = arr.indexOf(label);
                if (i >= 0) arr.splice(i, 1); else arr.push(label);
                next[q.id] = arr;
              } else {
                next[q.id] = on ? undefined : label;
              }
              set({ a: next });
            }
          };
        })
      };
    });

    var CONSENTS = [
      { id: 'data', label: 'Speicherung meiner Kundendaten', desc: 'Name, Kontakt und Besuche in der Kundenakte des Salons.' },
      { id: 'health', label: 'Speicherung meiner Gesundheitsangaben', desc: 'Unverträglichkeiten, Haarausfall und Medikamente.' },
      { id: 'photoDoc', label: 'Fotos für die Dokumentation', desc: 'Vorher-Nachher-Bilder, nur für das Team sichtbar.' },
      { id: 'photoSocial', label: 'Fotos für Social Media und Werbung', desc: 'Veröffentlichung durch den Salon, zum Beispiel auf Instagram.' }
    ];
    var consents = CONSENTS.map(function (x) {
      var on = !!c[x.id];
      return {
        label: x.label, desc: x.desc, on: on, word: on ? 'Ja' : 'Nein',
        track: on ? accent : '#8A918C', knobX: on ? '28px' : '0px',
        toggle: function () { var n = Object.assign({}, c); n[x.id] = !on; set({ c: n }); }
      };
    });

    var val = function (id) { var v = a[id]; if (Array.isArray(v)) return v.length ? v.join(', ') : 'Keine Angabe'; return v || 'Keine Angabe'; };
    var yn = function (id) { return c[id] ? 'Ja' : 'Nein'; };
    var origin = 'Heute neu ausgefüllt';
    if (ret) origin = (a.chHair === 'Ja' || a.chHealth === 'Ja') ? 'Heute aktualisiert' : 'Vom 20.10.2026 übernommen';
    var summary = [
      { k: 'Angaben', v: origin },
      { k: 'Zuletzt gefärbt', v: val('last') },
      { k: 'Wunschziel', v: val('goal') },
      { k: 'Auf keinen Fall', v: val('nogo') },
      { k: 'Zeit', v: val('time') },
      { k: 'Budget', v: val('budget') },
      { k: 'Fotos', v: 'Doku: ' + yn('photoDoc') + ' · Social Media: ' + yn('photoSocial') }
    ];
    var warnings = [];
    if (a.allergy === 'Ja') warnings.push({ text: 'Unverträglichkeit oder Allergie angegeben' });
    if (a.henna === 'Ja') warnings.push({ text: 'Henna oder Pflanzenfarbe im Haar' });
    if (a.keratin === 'Ja') warnings.push({ text: 'Keratin-Glättung im Haar' });
    if (a.spray === 'Ja') warnings.push({ text: 'Aufheller-Spray verwendet' });
    if (a.home === 'Ja') warnings.push({ text: 'Zuhause selbst gefärbt' });
    if (a.loss === 'Ja') warnings.push({ text: 'Haarbruch oder Haarausfall angegeben' });
    if (a.meds === 'Ja') warnings.push({ text: 'Medikamente oder gesundheitliche Besonderheiten' });
    var hasWarn = warnings.length > 0;
    if (!hasWarn) warnings.push({ text: 'Die Kundin hat nichts angegeben, was beim Färben zu beachten wäre.' });

    var inForm = idx >= 0;
    var staffMode = step === 0 || step === 8 || step === 10;
    var sig1 = !!st.sig1, sig2 = !!st.sig2;

    return {
      accent: accent,
      isStart: step === 0, isNew: step === 12, isWelcome: step === 1,
      q: q, onSearch: function (e) { set({ q: e.target.value }); },
      showUpload: !loaded && !needle, showStatus: loaded && !needle, showEmpty: !!needle && shown.length === 0,
      load: function () { set({ loaded: true }); },
      toNew: function () { set({ step: 12, newName: '', newPhone: '', q: '' }); },
      newName: st.newName || '', newPhone: st.newPhone || '',
      onName: function (e) { set({ newName: e.target.value }); },
      onPhone: function (e) { set({ newPhone: e.target.value }); },
      startNew: function () { set({ cust: 'new', ret: false, step: 1, svc: '', price: 0, a: {}, c: {}, sig1: false, sig2: false }); },
      svcOpts: svcOpts,
      svcHint: svc ? ('Dauer etwa ' + svc.dur + ' · Katalogpreis ' + svc.min + ' bis ' + svc.max + ' €') : 'Bitte zuerst eine Leistung wählen.', isQ: (step >= 2 && step <= 5) || step === 11, isConsent: step === 6,
      welcomeHead: ret ? 'Schön, Sie wiederzusehen, ' + cust.first + '.' : 'Willkommen, ' + cust.first + '.',
      welcomeText: ret ? 'Ihre Angaben vom letzten Besuch haben wir noch. Wir fragen nur kurz, ob sich etwas geändert hat. Das dauert etwa 30 Sekunden.' : 'Ein paar kurze Fragen, damit wir heute optimal für Sie arbeiten können. Das dauert etwa zwei Minuten.',
      isHandback: step === 7, isStaff: step === 8, isAgree: step === 9, isDone: step === 10,
      showProgress: inForm, showNav: inForm,
      progLabel: 'Schritt ' + (idx + 1) + ' von ' + flow.length, progW: Math.round(((idx + 1) / flow.length) * 100) + '%',
      nextLabel: step === 1 ? 'Los geht es' : (isLast ? 'Absenden' : 'Weiter'),
      modeLabel: staffMode ? 'Friseuransicht' : 'Kundenansicht',
      modeBg: staffMode ? '#1C1F1E' : '#E6ECEA', modeFg: staffMode ? '#FFFFFF' : '#1C1F1E',
      customers: customers,
      custName: cust.name, custFirst: cust.first, custService: svc ? svc.label : 'Leistung noch offen', custTime: cust.time ? ('Termin ' + cust.time + ' Uhr') : 'ohne Termin',
      custDur: svc ? svc.dur : '–',
      personal: [
        { k: 'Name', v: cust.name }, { k: 'Telefon', v: cust.phone }, { k: 'E-Mail', v: cust.mail }, { k: 'Heute gebucht', v: svc ? svc.label : 'Besprechen wir gleich gemeinsam' }
      ],
      qTitle: page.title, qHint: page.hint, questions: questions,
      consents: consents,
      sig1: sig1, noSig1: !sig1, sig1Bd: sig1 ? accent : '#8A918C',
      sig2: sig2, noSig2: !sig2, sig2Bd: sig2 ? accent : '#8A918C',
      today: new Date().toLocaleDateString('de-DE'),
      summary: summary, warnings: warnings,
      warnTitle: hasWarn ? 'Vor dem Färben beachten' : 'Keine Warnhinweise',
      warnBg: hasWarn ? '#FFF1DC' : '#FFFFFF', warnBd: hasWarn ? '#B45309' : '#DDE0DC', warnFg: hasWarn ? '#7A3E00' : '#1C1F1E',
      price: price,
      priceDown: function () { if (svc) set({ price: Math.max(svc.min, price - 10) }); },
      priceUp: function () { if (svc) set({ price: Math.min(svc.max, price + 10) }); },
      next: function () { set({ step: isLast ? 7 : flow[idx + 1] }); },
      back: function () { set({ step: idx <= 0 ? 0 : flow[idx - 1] }); },
      sign1: function () { set({ sig1: !sig1 }); },
      sign2: function () { set({ sig2: !sig2 }); },
      toStaff: function () { set({ step: 8 }); },
      toAgree: function () { if (svc) set({ step: 9 }); },
      toDone: function () { set({ step: 10 }); },
      reset: function () { set({ step: 0, q: '', a: {}, c: {}, sig1: false, sig2: false }); }
    };
  }
}

    return Component;
  })(DCLogic);
  var comp = new Component();
  comp.props = { accent: ACCENT };

  var reg = [];
  function h(fn) { reg.push(fn); return ' data-h="' + (reg.length - 1) + '"'; }
  function e(s) { return String(s == null ? '' : s).replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;').replace(/"/g, '&quot;'); }
  var SIG = '<svg role="img" aria-label="Unterschrift" width="220" height="64" viewBox="0 0 220 64" fill="none" stroke="#1C1F1E" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M8 44c12-22 22-34 28-30 7 5-12 34-4 36 8 2 16-26 24-24 6 2-4 20 4 20 9 0 12-18 20-18 6 0 2 16 10 16 10 0 14-22 26-24 10-2 6 22 18 22 14 0 22-14 40-16 12-1 24 4 38 2"></path></svg>';
  var CHECK = '<svg aria-hidden="true" width="34" height="34" viewBox="0 0 24 24" fill="none" stroke="#FFFFFF" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12.5l4.5 4.5L19 7.5"></path></svg>';
  var ARROW = '<svg class="hide-s" aria-hidden="true" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#1C1F1E" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 6l6 6-6 6"></path></svg>';
  var WARN = '<svg aria-hidden="true" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3.5L2.5 20h19L12 3.5z"></path><path d="M12 10v4.5"></path><path d="M12 17.5v.2"></path></svg>';

  function chip(o, cls) {
    return '<button class="chip ' + (cls || '') + '"' + h(o.pick) + ' aria-pressed="' + (o.on ? 'true' : 'false') + '" style="background:' + o.bg + ';color:' + o.fg + ';border:1.5px solid ' + o.bd + '">' + e(o.label) + '</button>';
  }
  function signBox(signed, fn, bd, hint, v) {
    return '<button class="sign"' + h(fn) + ' style="border:1.5px dashed ' + bd + '">' +
      (signed ? SIG + '<div class="muted small">Unterschrieben am ' + e(v.today) + '</div>'
              : '<div><div style="font-weight:600">Hier tippen, um zu unterschreiben</div><div class="muted small">' + hint + '</div></div>') + '</button>';
  }

  function view(v) {
    var a = v.accent, o = '';
    o += '<div class="top"><div class="brand">MIRO HAIR</div><div class="row" style="gap:12px"><div class="muted hide-s" style="font-size:14px">Beispieldaten</div><div class="mode" style="background:' + v.modeBg + ';color:' + v.modeFg + '">' + v.modeLabel + '</div></div></div>';
    if (v.showProgress) o += '<div class="prog"><div class="lbl">' + v.progLabel + '</div><div class="bar"><div style="background:' + a + ';width:' + v.progW + '"></div></div></div>';
    o += '<div class="main">';

    if (v.isStart) {
      o += '<div class="col" style="gap:16px">';
      o += '<div class="row stack-s" style="align-items:flex-end;justify-content:space-between;gap:20px"><div><h1>Heute im Salon</h1><p class="muted">Kundin aus der Liste antippen, suchen oder neu anlegen. Dann das iPad übergeben.</p></div><button class="btn"' + h(v.toNew) + ' style="background:' + a + ';flex-shrink:0;white-space:nowrap">Neue Kundin</button></div>';
      o += '<input id="q" class="field" type="search" aria-label="Kundin suchen" placeholder="Kundin suchen: Name oder Handynummer" value="' + e(v.q) + '" data-i="onSearch">';
      if (v.showUpload) o += '<div class="row stack-s" style="padding:20px 24px;gap:20px;background:#fff;border:1.5px dashed #8A918C;border-radius:14px"><div style="flex-grow:1"><div style="font-weight:600">Liste von heute noch nicht geladen</div><div class="muted small">Die Excel-Datei aus Planity hochladen, dann erscheinen hier die Termine. Suche und Neuanlage gehen auch ohne Liste.</div></div><button class="btn ghost"' + h(v.load) + ' style="flex-shrink:0;white-space:nowrap">Planity-Liste laden</button></div>';
      if (v.showStatus) o += '<div class="row muted small" style="justify-content:space-between;gap:16px;flex-wrap:wrap"><div>Planity-Liste von heute geladen: 52 Termine, davon 18 mit Bogen, 3 neue Kunden</div><button' + h(v.load) + ' style="min-height:44px;padding:0 8px;border:none;background:transparent;font-size:15px;font-weight:600;color:#1C1F1E;text-decoration:underline">Erneut laden</button></div>';
      if (v.showEmpty) o += '<div class="card muted" style="padding:20px 24px">Keine Kundin mit diesem Namen gefunden. Über „Neue Kundin“ legen Sie sie an.</div>';
      o += '<div class="col" style="gap:12px">';
      v.customers.forEach(function (c) {
        o += '<button class="item"' + h(c.pick) + '><div class="time">' + e(c.time) + '</div><div style="flex:1 1 200px;min-width:0"><div style="font-weight:600;font-size:19px">' + e(c.name) + '</div><div class="muted small">' + e(c.sub) + '</div></div><div class="tag" style="background:' + c.tagBg + ';color:' + c.tagFg + '">' + e(c.tag) + '</div>' + ARROW + '</button>';
      });
      o += '</div></div>';
    }

    if (v.isNew) {
      o += '<div class="col" style="gap:22px;max-width:640px"><div><h1>Schön, dass Sie da sind.</h1><p class="muted">Bitte tragen Sie Ihren Namen und Ihre Handynummer ein. Daran erkennen wir Sie beim nächsten Besuch wieder.</p></div>';
      o += '<div class="col" style="gap:8px"><label for="newName" style="font-weight:600">Vor- und Nachname</label><input id="newName" class="field" type="text" autocomplete="off" value="' + e(v.newName) + '" data-i="onName"></div>';
      o += '<div class="col" style="gap:8px"><label for="newPhone" style="font-weight:600">Handynummer</label><input id="newPhone" class="field" type="tel" autocomplete="off" value="' + e(v.newPhone) + '" data-i="onPhone"></div>';
      o += '<div class="row" style="gap:12px"><button class="btn ghost"' + h(v.reset) + '>Zurück</button><button class="btn"' + h(v.startNew) + ' style="background:' + a + '">Weiter</button></div></div>';
    }

    if (v.isWelcome) {
      o += '<div class="col" style="gap:24px"><div><h1>' + e(v.welcomeHead) + '</h1><p class="muted" style="max-width:640px">' + e(v.welcomeText) + '</p></div><div class="card" style="padding:8px 24px;max-width:640px">';
      v.personal.forEach(function (r) { o += '<div class="kv"><div class="k">' + e(r.k) + '</div><div class="v">' + e(r.v) + '</div></div>'; });
      o += '<div class="muted small" style="padding:14px 0">Stimmt etwas nicht? Sagen Sie Ihrem Friseur Bescheid.</div></div></div>';
    }

    if (v.isQ) {
      o += '<div class="col" style="gap:22px"><div><h1>' + e(v.qTitle) + '</h1><p class="muted">' + e(v.qHint) + '</p></div>';
      v.questions.forEach(function (q) {
        o += '<div class="col" style="gap:10px"><div style="font-weight:600">' + e(q.label) + '</div><div class="row" style="flex-wrap:wrap;gap:10px">' + q.opts.map(function (x) { return chip(x); }).join('') + '</div></div>';
      });
      o += '</div>';
    }

    if (v.isConsent) {
      o += '<div class="col" style="gap:16px"><div><h1>Ihre Einwilligungen</h1><p class="muted">Jede Zustimmung gilt einzeln und lässt sich jederzeit widerrufen.</p></div><div class="card" style="padding:0 24px">';
      v.consents.forEach(function (c) {
        o += '<div class="row" style="gap:16px;padding:12px 0;border-bottom:1px solid #ECEEEB"><div style="flex-grow:1"><div style="font-weight:600">' + e(c.label) + '</div><div class="muted small">' + e(c.desc) + '</div></div><div style="width:40px;font-size:15px;font-weight:600">' + c.word + '</div><button' + h(c.toggle) + ' aria-pressed="' + (c.on ? 'true' : 'false') + '" aria-label="' + e(c.label) + '" style="width:64px;height:44px;flex-shrink:0;padding:0;border:none;background:transparent;display:flex;align-items:center"><div style="width:64px;height:36px;border-radius:18px;padding:4px;background:' + c.track + '"><div style="width:28px;height:28px;border-radius:14px;background:#fff;margin-left:' + c.knobX + '"></div></div></button></div>';
      });
      o += '</div>' + signBox(v.sig1, v.sign1, v.sig1Bd, 'In der fertigen App unterschreiben Sie mit dem Finger.', v) + '</div>';
    }

    if (v.isHandback) {
      o += '<div class="center"><div class="dot" style="background:' + a + '">' + CHECK + '</div><h1>Vielen Dank, ' + e(v.custFirst) + '.</h1><p class="muted" style="max-width:520px;margin:0">Bitte geben Sie das iPad jetzt Ihrem Friseur zurück. Ihre Antworten sieht nur das Team.</p><button class="btn ghost"' + h(v.toStaff) + '>Friseur: mit PIN öffnen</button></div>';
    }

    if (v.isStaff) {
      o += '<div class="two"><div class="col" style="gap:14px"><div><h1 style="font-size:28px">' + e(v.custName) + '</h1><p class="muted small" style="margin-top:4px">' + e(v.custService) + ' · heute, ' + e(v.custTime) + '</p></div><div class="card" style="padding:4px 20px">';
      v.summary.forEach(function (r) { o += '<div class="kv small"><div class="k">' + e(r.k) + '</div><div class="v">' + e(r.v) + '</div></div>'; });
      o += '</div></div><div class="col" style="gap:14px"><div class="col" style="background:' + v.warnBg + ';border:1.5px solid ' + v.warnBd + ';border-radius:14px;padding:16px 20px;gap:8px"><div class="row" style="gap:10px;font-weight:600;color:' + v.warnFg + '">' + WARN + '<div>' + v.warnTitle + '</div></div>';
      v.warnings.forEach(function (w) { o += '<div class="small">' + e(w.text) + '</div>'; });
      o += '</div><div class="card col" style="padding:18px 20px;gap:14px"><div style="font-weight:600">Leistungsvereinbarung</div><div class="row" style="flex-wrap:wrap;gap:8px">' + v.svcOpts.map(function (x) { return chip(x, 'sm'); }).join('') + '</div><div class="muted small">' + e(v.svcHint) + '</div>';
      o += '<div class="row" style="gap:14px"><button' + h(v.priceDown) + ' aria-label="Preis senken" style="width:48px;height:48px;border-radius:24px;border:1.5px solid #1C1F1E;background:#fff;font-size:24px;line-height:1;color:#1C1F1E">−</button><div class="big" style="width:130px;text-align:center">' + v.price + ' €</div><button' + h(v.priceUp) + ' aria-label="Preis erhöhen" style="width:48px;height:48px;border-radius:24px;border:1.5px solid #1C1F1E;background:#fff;font-size:24px;line-height:1;color:#1C1F1E">+</button></div>';
      o += '<button class="btn"' + h(v.toAgree) + ' style="background:' + a + '">Kundin bestätigen lassen</button></div></div></div>';
    }

    if (v.isAgree) {
      o += '<div class="col" style="gap:18px;max-width:720px"><div><h1>Das haben wir besprochen</h1><p class="muted">Bitte prüfen Sie Leistung und Preis und bestätigen Sie mit Ihrer Unterschrift.</p></div>';
      o += '<div class="card row" style="padding:20px 24px;gap:24px;flex-wrap:wrap"><div style="flex:1 1 200px"><div style="font-weight:600;font-size:19px">' + e(v.custService) + '</div><div class="muted small">Dauer etwa ' + e(v.custDur) + '</div></div><div class="big">' + v.price + ' €</div></div>';
      o += signBox(v.sig2, v.sign2, v.sig2Bd, 'Ich bin mit der Behandlung und dem Preis einverstanden.', v);
      o += '<div class="row" style="gap:12px"><button class="btn ghost"' + h(v.toStaff) + '>Zurück</button><button class="btn"' + h(v.toDone) + ' style="background:' + a + '">Bestätigen</button></div></div>';
    }

    if (v.isDone) {
      o += '<div class="center"><div class="dot" style="background:' + a + '">' + CHECK + '</div><h1>In der Kundenakte gespeichert</h1><p class="muted" style="max-width:560px;margin:0">Bogen, Einwilligungen und die Vereinbarung über ' + v.price + ' € liegen bei ' + e(v.custName) + '. Beim nächsten Besuch kommt nur noch der Kurz-Check.</p><button class="btn"' + h(v.reset) + ' style="background:' + a + '">Zurück zur Tagesliste</button></div>';
    }

    o += '</div>';
    if (v.showNav) o += '<div class="nav"><button class="btn ghost"' + h(v.back) + '>Zurück</button><button class="btn"' + h(v.next) + ' style="background:' + a + '">' + v.nextLabel + '</button></div>';
    else o += '<div style="height:28px;flex-shrink:0"></div>';
    return o;
  }

  var vals = null, lastStep = null;
  function paint() {
    var root = document.getElementById('app');
    var act = document.activeElement, fid = act && act.id, pos = null;
    try { if (fid && act.type !== 'tel') pos = act.selectionStart; } catch (x) {}
    reg = [];
    vals = comp.renderVals();
    root.innerHTML = view(vals);
    if (fid) { var el = document.getElementById(fid); if (el) { el.focus(); try { if (pos != null) el.setSelectionRange(pos, pos); } catch (x) {} } }
    var step = (comp.state || {}).step || 0;
    if (step !== lastStep) { lastStep = step; window.scrollTo(0, 0); }
  }
  if (typeof document !== 'undefined') {
    document.addEventListener('click', function (ev) {
      var t = ev.target.closest ? ev.target.closest('[data-h]') : null;
      if (t) { var fn = reg[+t.getAttribute('data-h')]; if (fn) fn(); }
    });
    document.addEventListener('input', function (ev) {
      var k = ev.target.getAttribute && ev.target.getAttribute('data-i');
      if (k && vals && vals[k]) vals[k]({ target: ev.target });
    });
    paint();
  }
  if (typeof module !== 'undefined') module.exports = { comp: comp, view: view };
})();
</script>
</body>
</html>
