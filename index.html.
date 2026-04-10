Import React, { useState, useEffect } from "react";

/**
 * نظام أوتاد الكشفي - الإصدار v8.5 (نسخة السيادة المطلقة)
 * تم التطوير بواسطة: عبدالله العرفه (المحقق الجنائي الرقمي)
 * مخصص لمدرسة القاسم بن محمد
 */

// --- مكون البطاقة (Info Modal) - حوكمة وتوثيق حي ---
const InfoModal = ({ info, db, date, onClose }) => {
  if (!info) return null;
  
  const live = db[date]?.[`${info.pId}:${info.id}`] || { 
    status: "غير مرصود", 
    score: "--", 
    editorName: "نظام أوتاد", 
    editTime: "--" 
  };
  
  return (
    <div style={{ position: "fixed", inset: 0, background: "rgba(0,0,0,0.95)", display: "flex", alignItems: "center", justifyContent: "center", zIndex: 4000, backdropFilter: "blur(12px)" }}>
      <div style={{ background: "#1e293b", padding: "40px", borderRadius: "35px", width: "90%", maxWidth: "450px", textAlign: "center", border: "2px solid #22d3ee", boxShadow: "0 0 30px rgba(34,211,238,0.2)" }}>
        <h3 style={{ color: "#22d3ee", marginBottom: "20px" }}>التحقق الرقمي النهائي</h3>
        <p style={{ fontSize: "24px", fontWeight: "bold", color: "white", marginBottom: "5px" }}>{info.n}</p>
        
        <div style={{ textAlign: "right", marginTop: "25px", color: "#94a3b8", background: "#0f172a", padding: "20px", borderRadius: "20px" }}>
          <p style={{ margin: "10px 0" }}>📌 الحالة الحالية: <span style={{ color: "white" }}>{live.status === "present" ? "حاضر ✅" : live.status === "absent" ? "غائب ❌" : "لم يرصد"}</span></p>
          <p style={{ margin: "10px 0" }}>📊 الدرجة المستحقة: <span style={{ color: "#22d3ee", fontWeight: "bold" }}>{live.score} / 10</span></p>
          <hr style={{ borderColor: "#1e293b" }} />
          <p style={{ margin: "10px 0", fontSize: "14px" }}>✍️ المحقق المسؤول: <span style={{ color: "#fbbf24" }}>{live.editorName}</span></p>
          <p style={{ margin: "10px 0", fontSize: "14px" }}>⏰ توقيت العملية: <span style={{ color: "white" }}>{live.editTime}</span></p>
        </div>
        
        <button onClick={onClose} style={{ marginTop: "30px", background: "#ef4444", color: "white", border: "none", padding: "12px 60px", borderRadius: "15px", fontWeight: "bold", cursor: "pointer" }}>إغلاق الملف</button>
      </div>
    </div>
  );
};

// --- قاعدة البيانات الثابتة (DATA) ---
const DATA = {
  unit: { name: "مدرسة القاسم بن محمد", chief: "عبدالله العرفه" },
  users: [
    { name: "سلمان الصويلح", id: "111", role: "admin" },
    { name: "معاذ الشنقيطي", id: "222", role: "admin" },
    { name: "عبدالله العرفه", id: "333", role: "admin" },
    { name: "الوليد الحازمي", id: "1158717536", role: "leader" },
    { name: "حاتم خريزي", id: "1152451256", role: "leader" },
    { name: "بسام قرادي", id: "1153930803", role: "leader" },
    { name: "وضاح الصويلح", id: "1148865378", role: "leader" }
  ],
  platoons: [
    { id: 1, name: "طليعة ١", color: "#f59e0b", leaderId: "1158717536", members: [{ n: "صالح سعيد صالح حبتور", id: "1149916643" }, { n: "حسن محمد حسن الشهري", id: "1146756604" }, { n: "ريان محمد احمد جعام", id: "1145192223" }, { n: "غازي ابراهيم على سعيد العجمي", id: "0111052173" }, { n: "يزيد يحي عيسي خال", id: "1157051739" }, { n: "زياد سعيد محمد آل احمد العجلاني", id: "1150537148" }, { n: "الوليد فيصل عبدالله الحازمي", id: "1158717536" }, { n: "فهد فيصل خالد المهيني", id: "1146194400" }, { n: "يحي علي يحيى شراحيلي", id: "1150983151" }, { n: "عزام حيدر حسن خبراني", id: "1149391128" }] },
    { id: 2, name: "طليعة ٢", color: "#22d3ee", leaderId: "1152451256", members: [{ n: "ياسر موسى يحي ابو حيه", id: "1152663553" }, { n: "حاتم هشام حمزه خريزي", id: "1152451256" }, { n: "محمد جابر علي آل جمحان عسيري", id: "1150570198" }, { n: "رياض محمد سليم الزهراني", id: "1151320379" }, { n: "ابراهيم فرحان جابر التليدي", id: "1151153754" }, { n: "غازي باني مفضى الفدعاني العنزي", id: "1152864144" }, { n: "صالح عبدالله علي الخثعمي", id: "1149997080" }, { n: "اصيل متعب مدعج العالي العتيبي", id: "1152223028" }, { n: "فواز سعيد عوض الشهراني", id: "1193372115" }, { n: "علي مرضي علي آل داحشه الغامدي", id: "1154592537" }] },
    { id: 3, name: "طليعة ٣", color: "#a78bfa", leaderId: "1153930803", members: [{ n: "بسام علي جابر قرادي", id: "1153930803" }, { n: "علي بندر علي الرمثي الشهراني", id: "1146153513" }, { n: "راكان سلمان علي شراحيلي", id: "1152356109" }, { n: "زايد محمد مفلح الفاضلي القحطاني", id: "1152130900" }, { n: "راشد سعيدان سعيد الراشدي", id: "1153093875" }, { n: "عبدالعزيز محمد مفلح الفاضلي القحطاني", id: "1147815250" }, { n: "عيسى غازي مسند العويمري الرشيدي", id: "1154277246" }, { n: "بدر عبدالله يحي خظي كعبي", id: "1147688624" }, { n: "عبدالله عادل عبدالله قشاش", id: "1152864557" }, { n: "حسام سعد عبدالله الشهراني", id: "1155606302" }] },
    { id: 4, name: "طليعة ٤", color: "#34d399", leaderId: "1148865378", members: [{ n: "مشعل محمد مرعي آل معمر القحطاني", id: "1145624308" }, { n: "مشاري محمد مرعي آل معمر القحطاني", id: "1145624290" }, { n: "وضاح ماجد سلمان الناصر الصويلح", id: "1148865378" }, { n: "محمد حسين حمد فقيه", id: "1149206243" }, { n: "فارس بريحي محمد العمري", id: "1148256413" }, { n: "رائد حسين علي حوباني", id: "1146847395" }, { n: "راكان حسين علي حوباني", id: "1146847387" }, { n: "عبدالله سعيد محمد آل عايض القرني", id: "1147807240" }, { n: "ناصر مفلح عواض الحضيري المطيري", id: "1145593594" }, { n: "مبارك مرزوق عبدالله خميس", id: "1145673271" }] }
  ]
};

export default function App() {
  const [user, setUser] = useState(null);
  const [loginId, setLoginId] = useState("");
  const [date, setDate] = useState(new Date().toISOString().split("T")[0]);
  const [db, setDb] = useState({});
  const [info, setInfo] = useState(null);
  const [msg, setMsg] = useState("");

  useEffect(() => {
    try {
      const saved = localStorage.getItem("awtad_v8_5_final");
      if (saved) setDb(JSON.parse(saved));
    } catch (e) {
      localStorage.removeItem("awtad_v8_5_final");
    }
  }, []);

  const toast = (t) => { setMsg(t); setTimeout(() => setMsg(""), 3000); };

  const handleLogin = () => {
    const found = DATA.users.find(u => u.id === loginId);
    if (found) { setUser(found); toast(`أهلاً بك يا مولاي ${found.name}`); }
    else alert("⚠️ السجل المدني غير موجود.");
  };

  const updateEntry = (pId, mId, field, val) => {
    const today = new Date().toISOString().split("T")[0];
    if (date > today) return alert("⚠️ لا يمكنك رصد المستقبل!");

    let cleanVal = val;
    if (field === "score") {
      cleanVal = val === "" ? "" : Math.min(Math.max(parseInt(val) || 0, 0), 10);
    }

    const entryKey = `${pId}:${mId}`;
    const newDb = { 
      ...db, 
      [date]: { 
        ...db[date], 
        [entryKey]: { 
          ...(db[date]?.[entryKey] || { status: null, score: 5 }), 
          [field]: cleanVal,
          editorName: user.name,
          editTime: new Date().toLocaleTimeString('ar-SA')
        } 
      } 
    };
    setDb(newDb);
    localStorage.setItem("awtad_v8_5_final", JSON.stringify(newDb));
  };

  const exportData = () => {
    const blob = new Blob([JSON.stringify(db, null, 2)], { type: "application/json" });
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    a.href = url;
    a.download = `awtad_report_${date}.json`;
    document.body.appendChild(a); a.click(); document.body.removeChild(a); 
    URL.revokeObjectURL(url); toast("تم التصدير الجنائي ✅");
  };

  if (!user) return (
    <div style={{ background: "#020617", height: "100vh", color: "white", display: "flex", flexDirection: "column", alignItems: "center", justifyContent: "center", fontFamily: "'Cairo', sans-serif" }}>
      <div style={{ fontSize: "100px" }}>⚜️</div>
      <h1 style={{ letterSpacing: "8px", textShadow: "0 0 25px #22d3ee" }}>أوتـاد</h1>
      <p style={{ color: "#94a3b8", marginBottom: "40px" }}>نظام السيادة الكشفية v8.5</p>
      <div style={{ background: "#1e293b", padding: "50px", borderRadius: "35px", border: "1px solid #334155", textAlign: "center" }}>
        <input type="password" placeholder="أدخل السجل المدني" value={loginId} onChange={e => setLoginId(e.target.value)} style={{ padding: "18px", borderRadius: "15px", width: "280px", background: "#020617", color: "white", fontSize: "24px", border: "2px solid #334155", textAlign: "center", outline: "none" }} />
        <br /><button onClick={handleLogin} style={{ marginTop: "30px", padding: "18px 90px", background: "#22d3ee", border: "none", borderRadius: "15px", fontWeight: "bold", cursor: "pointer", color: "#020617" }}>دخول</button>
      </div>
    </div>
  );

  return (
    <div style={{ direction: "rtl", padding: "20px", background: "#020617", minHeight: "100vh", color: "white", fontFamily: "'Cairo', sans-serif" }}>
      {msg && <div style={{ position: "fixed", top: "20px", left: "50%", transform: "translateX(-50%)", background: "#065f46", padding: "12px 40px", borderRadius: "15px", zIndex: 5000 }}>{msg}</div>}
      
      <header style={{ display: "flex", justifyContent: "space-between", alignItems: "center", background: "#1e293b", padding: "25px", borderRadius: "25px", marginBottom: "30px", border: "1px solid #334155" }}>
        <div><h2 style={{ margin: 0, color: "#22d3ee" }}>{DATA.unit.name}</h2><span>المحقق المسؤول: {user.name} 🎖️</span></div>
        <div style={{ display: "flex", gap: "12px" }}>
            <button onClick={exportData} style={{ background: "#065f46", color: "white", border: "none", padding: "12px 20px", borderRadius: "15px", cursor: "pointer" }}>📂 تصدير</button>
            <button onClick={() => setUser(null)} style={{ background: "#7f1d1d", color: "white", border: "none", padding: "12px 20px", borderRadius: "15px", cursor: "pointer" }}>خروج</button>
        </div>
      </header>

      <div style={{ textAlign: "center", marginBottom: "40px" }}>
        <input type="date" max={new Date().toISOString().split("T")[0]} value={date} onChange={e => setDate(e.target.value)} style={{ background: "#1e293b", color: "white", border: "1px solid #22d3ee", padding: "12px", borderRadius: "15px" }} />
      </div>

      {DATA.platoons.map(p => {
        if (user.role !== "admin" && p.leaderId !== user.id) return null;
        return (
          <div key={p.id} style={{ border: `1px solid ${p.color}44`, borderRadius: "30px", padding: "25px", marginTop: "40px", background: "#0f172a" }}>
            <h3 style={{ color: p.color, borderBottom: `2px solid ${p.color}`, paddingBottom: "15px" }}>{p.name}</h3>
            {p.members.filter(m => m.id !== user.id).map(m => {
              const rec = db[date]?.[`${p.id}:${m.id}`] || { status: null, score: 5 };
              return (
                <div key={m.id} style={{ display: "flex", alignItems: "center", gap: "15px", padding: "18px 0", borderBottom: "1px solid #1e293b" }}>
                  <span style={{ flex: 1, fontWeight: "bold" }}>{m.n}</span>
                  <button onClick={() => setInfo({ ...m, pId: p.id })} style={{ background: "none", border: "none", cursor: "pointer", fontSize: "24px" }}>🕵️‍♂️</button>
                  <select value={rec.status || ""} onChange={e => updateEntry(p.id, m.id, "status", e.target.value)} style={{ background: rec.status === "present" ? "#065f46" : rec.status === "absent" ? "#7f1d1d" : "#334155", color: "white", borderRadius: "12px", padding: "10px", border: "none" }}>
                    <option value="">؟</option><option value="present">حاضر</option><option value="absent">غائب</option>
                  </select>
                  <input type="number" value={rec.score} onInput={e => e.target.value = e.target.value.slice(0, 2)} onChange={e => updateEntry(p.id, m.id, "score", e.target.value)} style={{ width: "65px", background: "#020617", color: "#22d3ee", borderRadius: "12px", padding: "10px", textAlign: "center", border: "1px solid #334155" }} />
                </div>
              );
            })}
          </div>
        );
      })}

      <InfoModal info={info} db={db} date={date} onClose={() => setInfo(null)} />
      <footer style={{ textAlign: "center", padding: "60px 0 30px", color: "#1e293b", fontSize: "12px" }}>AWTAD SYSTEM - V8.5 FINAL - 2026</footer>
    </div>
  );
}
