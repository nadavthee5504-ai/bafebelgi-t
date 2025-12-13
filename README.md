
<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>וופל בלגי על מקל | הזמנה</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --waffle-color: #ff9f47;
            --waffle-bg: #fff4e4;
            --main-font: 'Heebo', sans-serif;
        }

        body { 
            font-family: var(--main-font);
            background: #ffe9d1;
            margin: 0;
            padding: 0;
            direction: rtl;
        }

        .box {
            max-width: 600px;
            margin: 20px auto;
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .title {
            font-size: 36px;
            font-weight: 700;
            text-align: center;
            margin: 20px 0 10px;
            color: #4a2c1b;
        }

        .price {
            text-align: center;
            font-size: 20px;
            margin-bottom: 15px;
            color: #884a22;
        }
        
        .phone-link-container {
            text-align: center; 
            margin-bottom: 25px;
        }
        .phone-link {
            color: #4a2c1b; 
            font-weight: bold; 
            text-decoration: none; 
            border: 1px solid #ff9f47; 
            padding: 8px 15px; 
            border-radius: 8px; 
            background-color: #fff3e6;
            display: inline-block;
            transition: background-color 0.2s;
        }
        .phone-link:hover {
            background-color: var(--waffle-color);
            color: white;
        }

        label { 
            font-weight: 700; 
            margin-top: 20px; 
            display: block; 
            color: #333; 
        }

        input:not([type="radio"]):not([type="checkbox"]), textarea {
            width: 100%;
            padding: 12px;
            margin-top: 5px;
            border-radius: 8px;
            border: 1px solid #ddd;
            transition: border-color 0.3s;
            box-sizing: border-box; 
        }
        
        input[type="time"] { 
            max-width: 150px;
        }

        .waffle-box {
            background: var(--waffle-bg);
            padding: 18px;
            border-radius: 12px;
            margin-top: 20px;
            border: 1px solid #ff9f4730;
        }
        
        .waffle-box b {
            font-size: 18px;
            color: #4a2c1b;
            display: block;
            margin-bottom: 5px;
        }
        
        /* סטייל התוספות (צ'קבוקס) */
        .waffle-box input[type="checkbox"] { display: none; }

        .waffle-box input[type="checkbox"] + label {
            background-color: #f7f7f7;
            padding: 8px 15px;
            border-radius: 20px;
            border: 1px solid #ddd;
            display: inline-block;
            margin-left: 5px;
            margin-bottom: 10px;
            cursor: pointer;
            transition: all 0.2s;
            font-size: 15px;
            font-weight: 500;
        }

        .waffle-box input[type="checkbox"]:checked + label {
            background-color: var(--waffle-color);
            color: white;
            border-color: var(--waffle-color);
            box-shadow: 0 2px 4px #0003;
            transform: scale(1.05);
        }

        .topping-group {
            margin-top: 15px;
            margin-bottom: 15px;
            font-weight: normal;
            border-top: 1px dashed #ff9f4760;
            padding-top: 10px;
        }

        .topping-group:first-child {
            border-top: none;
            padding-top: 0;
        }
        
        /* סטייל אמצעי תשלום (רדיו) */
        .payment-selection-group {
            margin-top: 10px;
        }
        
        .payment-selection-group input[type="radio"] { 
            display: none; 
        }

        .payment-selection-group input[type="radio"] + label {
            background-color: #f7f7f7;
            padding: 10px 18px; 
            border-radius: 25px; 
            border: 1px solid #ddd;
            display: inline-block;
            margin-left: 10px;
            margin-bottom: 10px;
            cursor: pointer;
            transition: all 0.2s;
            font-size: 16px;
            font-weight: 500;
        }

        .payment-selection-group input[type="radio"]:checked + label {
            background-color: var(--waffle-color);
            color: white;
            border-color: var(--waffle-color);
            box-shadow: 0 2px 4px #0003;
            transform: scale(1.05);
        }
        
        .btn {
            width: 100%;
            background: var(--waffle-color);
            padding: 16px;
            border-radius: 10px;
            color: white;
            font-weight: 700;
            font-size: 19px;
            border: none;
            margin-top: 30px;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(255, 159, 71, 0.4);
            transition: background 0.2s, transform 0.1s;
        }
        
        .total-display {
            margin-top:15px; 
            font-weight:700; 
            font-size: 22px; 
            padding: 10px; 
            border-radius: 8px;
            background-color: #fff3e6;
            color: #4a2c1b;
            text-align: center;
        }
        
        .payment-section-hidden {
            display: none !important;
        }
        
        .payment-options-container {
            transition: opacity 0.3s;
        }
        
        .payment-info {
            background: #fff3c4;
            padding: 12px;
            border-radius: 10px;
            margin-top: 10px;
            display: none;
            font-weight: 700;
            color: #d67a00;
            border-left: 5px solid var(--waffle-color);
        }
        
        .required-star {
            color: red;
            font-size: 14px;
            margin-right: 5px;
        }
        
        .error-border {
            border: 2px solid red !important;
        }
        .error-text {
            color: red;
            font-size: 12px;
            margin-top: -5px;
            display: none;
        }

        /* --- CSS לשליחת קבלה --- */
        .receipt-box{
            display:none;
            margin-top:12px;
            background:#eafff0;
            border:1px solid #b8f3cc;
            padding:10px;
            border-radius:10px;
            font-weight:bold;
            text-align:center;
        }
        .receipt-box a{
            display:inline-block;
            margin-top:8px;
            background:#25D366; /* צבע ירוק של ווטסאפ */
            color:white;
            padding:10px 12px;
            border-radius:10px;
            text-decoration:none;
        }
        /* -------------------------- */
        
    </style>
</head>
<body>

<div class="box">

    <div class="title">וופל בלגי על מקל 🧇</div>
    <div class="price">מחיר בסיס: 7 ש"ח לוופל</div>
    
    <div class="phone-link-container">
        <a href="tel:972553085504" class="phone-link">
            📞 התקשרו אלינו: 055-3085504
        </a>
    </div>
    
    <label for="name">שם: <span class="required-star">*</span></label>
    <input id="name" required>
    <div id="error-name" class="error-text">שדה חובה</div>

    <label for="phone">טלפון: <span class="required-star">*</span></label>
    <input id="phone" type="tel" required> 
    <div id="error-phone" class="error-text">שדה חובה</div>
    
    <label for="time">שעה רצויה לאיסוף:</label>
    <input id="time" type="time">
    <div id="error-time" class="error-text"></div>
    <hr style="margin: 25px 0; border: 0; border-top: 2px dashed #ff9f4760;">

    <label for="qty">כמות וופלים:</label>
    <input id="qty" type="number" min="0" value="0">
    <div id="error-qty" class="error-text">נא לבחור לפחות וופל אחד, או למלא הערות כלליות.</div>

    <div id="total" class="total-display">
        סה"כ: 0 ש"ח
    </div>

    <div id="waffles">
        </div>
    <div id="payment-section" class="payment-options-container payment-section-hidden">
        <label>אמצעי תשלום: <span class="required-star">*</span></label>
        
        <div id="payment-options" class="payment-selection-group">
            <input type="radio" name="pay" value="ביט" id="pay_bit"><label for="pay_bit"> 📲 ביט</label>
            <input type="radio" name="pay" value="פייבוקס" id="pay_fb"><label for="pay_fb"> 📱 פייבוקס</label>
            <input type="radio" name="pay" value="מזומן" id="pay_cash"><label for="pay_cash"> 💵 מזומן</label>
        </div>
        <div id="error-pay" class="error-text">נא לבחור אמצעי תשלום</div>

        <div id="paymentInfo" class="payment-info"></div>
        
        <div id="paymentUploadInfo" class="payment-upload-info">
            **חשוב:** לאחר שליחת ההודעה, אנא חזור לשיחה וצרף את תמונת אישור התשלום (קבלה/צילום מסך) לוואטסאפ.
        </div>
    </div>
    <label for="notes">הערות (חובה למלא אם הכמות 0):</label>
    <textarea id="notes" placeholder="כאן ניתן להוסיף הערות כלליות להזמנה..."></textarea>

    <button id="sendBtn" class="btn" onclick="sendUnifiedOrder()">שליחת הזמנה לוואטסאפ</button>
    <button class="btn" style="background: #ccc; margin-top: 10px;" onclick="resetForm()">איפוס טופס</button>
    
    <div id="receiptBox" class="receipt-box">
        כדי לשלוח קבלה ללקוח לחץ כאן:
        <br>
        <a id="receiptLink" href="#" target="_blank">שלח קבלה ללקוח</a>
    </div>
    </div>

<script>
const PRICE = 7;
const MY_PHONE_NUMBER = "972553085504"; 

// פונקציה להמרת מספר טלפון לפורמט ווטסאפ בינלאומי
function toWaNumber(phone) {
  let d = (phone || "").replace(/\D/g, "");
  if (d.startsWith("972")) return d;
  if (d.startsWith("0")) return "972" + d.slice(1);
  if (d.length === 9 && d.startsWith("5")) return "972" + d;
  return d;
}

function generateOrderId() {
    const now = new Date();
    // פורמט תאריך: YYMMDD
    const datePart = now.getFullYear().toString().slice(2) + 
                     (now.getMonth() + 1).toString().padStart(2, '0') + 
                     now.getDate().toString().padStart(2, '0');
    // פורמט זמן: HHmmss
    const timePart = now.getHours().toString().padStart(2, '0') + 
                     now.getMinutes().toString().padStart(2, '0') + 
                     now.getSeconds().toString().padStart(2, '0');
    // קוד מלא: WAFFLE-YYMMDD-HHmmss
    return `WAFFLE-${datePart}-${timePart}`;
}

function updateWaffles() {
    const qtyInput = document.getElementById("qty");
    let qty = Number(qtyInput.value);
    const paymentSection = document.getElementById("payment-section");

    if (qty < 0 || isNaN(qty)) {
        qty = 0;
        qtyInput.value = 0;
    }
    
    document.getElementById("total").innerText = "סה\"כ: " + (qty * PRICE) + " ש\"ח";

    // הסתרת/הצגת אפשרויות תשלום בהתאם לכמות
    if (qty > 0) {
        paymentSection.classList.remove("payment-section-hidden");
    } else {
        paymentSection.classList.add("payment-section-hidden");
        document.getElementById("paymentInfo").style.display = "none";
        document.getElementById("paymentUploadInfo").style.display = "none";
        document.querySelectorAll('input[name="pay"]').forEach(radio => radio.checked = false);
    }
    
    let html = "";
    for (let i = 1; i <= qty; i++) {
        html += `
            <div class="waffle-box">
                <b>🧇 וופל #${i}</b>
                <div class="topping-group">
                    <label>רטבים:</label>
                    <input type="checkbox" id="sauce_choc_${i}" name="sauce_${i}" value="סירופ שוקולד"><label for="sauce_choc_${i}">🍫 סירופ שוקולד</label>
                    <input type="checkbox" id="sauce_maple_${i}" name="sauce_${i}" value="סירופ מייפל"><label for="sauce_maple_${i}">🥞 סירופ מייפל</label>
                    <input type="checkbox" id="sauce_milk_${i}" name="sauce_${i}" value="ריבת חלב"><label for="sauce_milk_${i}">🥛 ריבת חלב</label>
                </div>
                <div class="topping-group">
                    <label>תוספות :</label>
                    <input type="checkbox" id="top_oreo_${i}" name="top_${i}" value="אוראו"><label for="top_oreo_${i}">⚫ אוראו</label>
                    <input type="checkbox" id="top_lotus_${i}" name="top_${i}" value="לוטוס"><label for="top_lotus_${i}">🍪 לוטוס</label>
                    <input type="checkbox" id="top_click_${i}" name="top_${i}" value="קליק"><label for="top_click_${i}">✨ קליק</label>
                    <input type="checkbox" id="top_lentils_${i}" name="top_${i}" value="עדשים"><label for="top_lentils_${i}">🟢 עדשים</label>
                </div>
                <div class="topping-group">
                    <label>מעל :</label>
                    <input type="checkbox" id="extra_cream_${i}" name="extra_${i}" value="קצפת"><label for="extra_cream_${i}">🍦 קצפת</label>
                    <input type="checkbox" id="extra_sug_${i}" name="extra_${i}" value="סוכריות"><label for="extra_sug_${i}">🍬 סוכריות</label>
                </div>
            </div>
        `;
    }
    document.getElementById("waffles").innerHTML = html;
}

document.getElementById("qty").addEventListener("input", updateWaffles);
document.addEventListener("DOMContentLoaded", updateWaffles);


function resetForm() {
    if (confirm("האם אתה בטוח שברצונך לאפס את כל פרטי הטופס?")) {
        document.getElementById("name").value = "";
        document.getElementById("phone").value = "";
        document.getElementById("time").value = "";
        document.getElementById("qty").value = 0;
        document.getElementById("notes").value = "";

        document.querySelectorAll('input[name="pay"]').forEach(radio => radio.checked = false);
        
        document.getElementById("paymentInfo").style.display = "none";
        document.getElementById("paymentUploadInfo").style.display = "none";
        document.getElementById("receiptBox").style.display = "none"; 
        
        document.querySelectorAll('.error-text').forEach(el => el.style.display = "none");
        document.querySelectorAll('input, textarea, #payment-options').forEach(el => el.classList.remove("error-border"));

        updateWaffles();
    }
}

function validateField(id, errorTextId, validationFn, errorMessage) {
    const input = document.getElementById(id);
    const errorEl = document.getElementById(errorTextId);
    let isValid = validationFn(input.value);

    if (!isValid) {
        input.classList.add("error-border");
        errorEl.innerText = errorMessage;
        errorEl.style.display = "block";
    } else {
        input.classList.remove("error-border");
        errorEl.style.display = "none";
    }
    return isValid;
}


function sendUnifiedOrder() {
    const sendBtn = document.getElementById('sendBtn');
    
    if (sendBtn.disabled) {
        return;
    }
    
    // --- וולידציה ---
    const name = document.getElementById("name").value.trim();
    const phone = document.getElementById("phone").value.trim();
    const time = document.getElementById("time").value.trim(); 
    const pay = document.querySelector('input[name="pay"]:checked');
    const qty = Number(document.getElementById("qty").value);
    const notes = document.getElementById("notes").value.trim();

    let isFormValid = true;

    // ולידציה על שם (חובה)
    if (!validateField("name", "error-name", v => v.length > 0, "נא למלא את השם.")) isFormValid = false;
    
    // ולידציה על טלפון (חובה + בדיקת תקינות בסיסית)
    // בדיקה שהוזנו לפחות 7 ספרות (מנקה תווים שאינם ספרות לפני הבדיקה)
    if (!validateField("phone", "error-phone", v => v.replace(/\D/g, "").length >= 7, "נא למלא טלפון תקין (מינימום 7 ספרות).")) isFormValid = false;

    // ולידציה לכמות/הערות (חובה לפחות אחד מהם)
    if (qty === 0 && notes.length === 0) {
        document.getElementById("qty").classList.add("error-border");
        document.getElementById("error-qty").innerText = "אם הכמות 0, יש למלא הערות כלליות (למשל, לתיאום שעה/בירור).";
        document.getElementById("error-qty").style.display = "block";
        document.getElementById("notes").classList.add("error-border");
        isFormValid = false;
    } else {
        document.getElementById("qty").classList.remove("error-border");
        document.getElementById("error-qty").style.display = "none";
        document.getElementById("notes").classList.remove("error-border");
    }

    const errorPayEl = document.getElementById("error-pay");
    const paymentOptionsEl = document.getElementById("payment-options");

    // תשלום נדרש רק אם יש וופלים
    if (qty > 0 && !pay) {
        paymentOptionsEl.classList.add("error-border");
        errorPayEl.style.display = "block";
        isFormValid = false;
    } else if (pay) {
        paymentOptionsEl.classList.remove("error-border");
        errorPayEl.style.display = "none";
    }


    if (!isFormValid) {
        alert("נא לתקן את השדות המסומנים באדום לפני השליחה.");
        return;
    }

    // --- מניעת שליחה כפולה ---
    sendBtn.disabled = true; 
    sendBtn.innerText = "שולח הזמנה, נא להמתין...";

    // --- יצירת קוד הזמנה ---
    const orderId = generateOrderId();
    
    // --- נתוני הזמנה ---
    const totalPrice = qty * PRICE;
    const paymentStatus = pay ? pay.value : 'לא רלוונטי (כמות 0)';
    
    // אובייקט נתונים מוכן ל-Google Sheets/אחסון (orderDetails)
    const orderDetails = {
        orderId: orderId,
        customerName: name,
        customerPhone: phone,
        pickupTime: time || 'לא צוין',
        quantity: qty,
        totalPrice: totalPrice,
        paymentMethod: paymentStatus,
        notes: notes,
        waffles: []
    };
    
    // מילון לאיסוף סיכום כל התוספות
    const toppingSummary = {};

    // איסוף נתוני הוופלים
    for (let i = 1; i <= qty; i++) {
        // איסוף כל התוספות הנבחרות לוופל הנוכחי
        const sauces = [...document.querySelectorAll(`input[name="sauce_${i}"]:checked`)]
                        .map(x => x.value);
        const tops = [...document.querySelectorAll(`input[name="top_${i}"]:checked`)]
                        .map(x => x.value);
        const extras = [...document.querySelectorAll(`input[name="extra_${i}"]:checked`)]
                        .map(x => x.value);

        // עדכון סיכום התוספות
        [...sauces, ...tops, ...extras].forEach(item => {
            toppingSummary[item] = (toppingSummary[item] || 0) + 1;
        });

        // שמירה באובייקט orderDetails לטובת פירוט הוופלים
        orderDetails.waffles.push({
            id: i,
            sauces: sauces.join(", ") || "ללא רטבים",
            toppings: tops.join(", ") || "ללא תוספות",
            extras: extras.join(", ") || "ללא פיניש"
        });
    }

    // --- יצירת סיכום תוספות טקסטואלי ---
    let summaryMsg = '';
    const summaryKeys = Object.keys(toppingSummary);
    if (summaryKeys.length > 0 && qty > 0) {
        summaryMsg += `*** 📝 סיכום למטבח: ***\n`;
        summaryKeys.forEach(key => {
            summaryMsg += `*סה"כ ${key}:* ${toppingSummary[key]}\n`;
        });
        summaryMsg += `==============================\n`;
    }


    // 1. יצירת הודעת האישור שאתה שולח ללקוח (נוסח העתק/הדבק)
    const confirmationMsgForCopy = `
*--- ✂️ התחל העתקה לכאן ✂️ ---*
שלום ${orderDetails.customerName}, תודה רבה על הזמנתך! 🙏

*קוד הזמנה:* ${orderDetails.orderId}
*מספר פריטים:* ${orderDetails.quantity} וופלים
*סה"כ לתשלום:* ${orderDetails.totalPrice} ש"ח
*שעת איסוף רצויה:* ${orderDetails.pickupTime} ${orderDetails.pickupTime !== 'לא צוין' ? '⏰' : ''}
*אמצעי תשלום:* ${orderDetails.paymentMethod}

נשתדל להכין את ההזמנה בדיוק בשעה שציינת.
${pay && pay.value !== "מזומן" ? 'נא לא לשכוח לצרף אישור תשלום.' : ''}
מחכים לך! 😊
*--- 🛑 סיים העתקה לכאן 🛑 ---*
`;


    // 2. יצירת הודעת ההזמנה שנשלחת אליך (העסק)
    let orderMsg = `[ORDER_ID: ${orderDetails.orderId}]
🔔 *הזמנה חדשה (וופל בלגי)* 🔔
==============================
${summaryMsg}
*קוד הזמנה*: ${orderDetails.orderId}
*פרטי לקוח:*
👤 *שם*: ${orderDetails.customerName}
📞 *טלפון*: ${orderDetails.customerPhone}
⏰ *שעה רצויה לאיסוף*: ${orderDetails.pickupTime}
💰 *סה"כ לתשלום*: ${orderDetails.totalPrice} ש"ח
💵 *אמצעי תשלום*: ${orderDetails.paymentMethod}
==============================
*פירוט ההזמנה:*
`;
    
    if (orderDetails.quantity === 0) {
        orderMsg += `
*אין וופלים בהזמנה זו.* (פנייה כללית).
`;
    } else {
        orderDetails.waffles.forEach(waffle => {
            orderMsg += `
*וופל #${waffle.id}*:
🍫 רטבים: ${waffle.sauces}
🍬 תוספות: ${waffle.toppings}
✨ מעל: ${waffle.extras}
`;
        });
    }
    
    if (orderDetails.notes) orderMsg += `\n📝 *הערות כלליות*: ${orderDetails.notes}`;
    
    orderMsg += `
==============================
${pay && pay.value !== "מזומן" ? '🔴 *הערה לתשלום:* הלקוח מתבקש לצרף אישור תשלום מיד.' : ''}
${confirmationMsgForCopy}
`;
    
    
    // 3. שליחה לווטסאפ אליך (העסק)
    const orderUrl = "https://wa.me/" + MY_PHONE_NUMBER + "?text=" + encodeURIComponent(orderMsg);
    window.open(orderUrl, "_blank");
    
    
    // --- לוגיקה ליצירת קבלה ללקוח (לחצן) ---
    const customerWa = toWaNumber(orderDetails.customerPhone);
    const receiptMsg = `✅ קבלה - וופל בלגי על מקל

*קוד הזמנה*: ${orderDetails.orderId}
*סה"כ*: ${orderDetails.totalPrice} ש"ח
*אמצעי תשלום*: ${orderDetails.paymentMethod}
*שעה*: ${orderDetails.pickupTime}

*פירוט*:
` + orderDetails.waffles.map(w =>
      `🧇 וופל #${w.id}
🍫 ${w.sauces}
🍬 ${w.toppings}
✨ ${w.extras}`
    ).join("\n\n");
    
    const receiptUrl = "https://wa.me/" + customerWa + "?text=" + encodeURIComponent(receiptMsg);
    document.getElementById("receiptLink").href = receiptUrl;
    document.getElementById("receiptBox").style.display = "block";
    // --------------------------------------------------------


    // איפוס הכפתור לאחר שליחה
    setTimeout(() => {
        sendBtn.disabled = false;
        sendBtn.innerText = "שליחת הזמנה לוואטסאפ";
    }, 1500);
}

// הצגת מספרי תשלום
document.querySelectorAll('input[name="pay"]').forEach(r => {
    r.addEventListener("change", () => {
        const val = r.value;
        let txt = "";
        const uploadBox = document.getElementById("paymentUploadInfo");

        if (val === "ביט") {
            txt = "📲 מספר לתשלום בביט: 050-6205953";
            uploadBox.style.display = "block";
        } else if (val === "פייבוקס") {
            txt = "📲 מספר לתשלום בפייבוקס: 054-2296540";
            uploadBox.style.display = "block";
        } else if (val === "מזומן") {
            txt = "💵 תשלום אצל משפחת טי";
            uploadBox.style.display = "none";
        }

        const infoBox = document.getElementById("paymentInfo");
        infoBox.innerText = txt;
        infoBox.style.display = "block";
    });
});
</script>

</body>
</html>
