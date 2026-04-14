<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sinfdoshlar Uchun</title>
    <style>
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f0f2f5; margin: 0; display: flex; justify-content: center; align-items: center; min-height: 100vh; }
        .container { background: white; padding: 30px; border-radius: 15px; box-shadow: 0 10px 25px rgba(0,0,0,0.1); width: 90%; max-width: 400px; text-align: center; }
        h1 { color: #1a73e8; }
        input { width: 100%; padding: 12px; margin: 10px 0; border: 1px solid #ddd; border-radius: 8px; box-sizing: border-box; }
        button { width: 100%; padding: 12px; background-color: #1a73e8; color: white; border: none; border-radius: 8px; cursor: pointer; font-size: 16px; transition: 0.3s; }
        button:hover { background-color: #1557b0; }
        #book-shelf { display: none; text-align: left; }
        .book-card { background: #fff; border-bottom: 1px solid #eee; padding: 15px 0; display: flex; justify-content: space-between; align-items: center; }
        .book-info h3 { margin: 0; font-size: 16px; color: #333; }
        .book-info p { margin: 5px 0 0; font-size: 14px; color: #777; }
        .read-btn { background: #34a853; width: auto; padding: 5px 15px; font-size: 14px; }
        .error { color: red; font-size: 14px; margin-bottom: 10px; display: none; }
    </style>
</head>
<body>

<div class="container" id="login-box">
    <h1>Sinfdoshlar Uchun</h1>
    <p>Kirish uchun parolni kiriting:</p>
    <div id="error-msg" class="error">Parol noto'g'ri!</div>
    <input type="password" id="password" placeholder="Parol...">
    <button onclick="checkPassword()">Kirish</button>
</div>

<div class="container" id="book-shelf">
    <h1>Kutubxona</h1>
    <div id="book-list">
        </div>
</div>

<script>
    const books = [
        { title: "Sariq devni minib", author: "Xudoyberdi To'xtaboyev", link: "#" },
        { title: "Dunyoning ishlari", author: "O'tkir Hoshimov", link: "#" },
        { title: "O'tkan kunlar", author: "Abdulla Qodiriy", link: "#" },
        { title: "Yulduzli tunlar", author: "Pirimqul Qodirov", link: "#" },
        { title: "Kichik shahzoda", author: "Antuan de Sent-Ekzyuperi", link: "#" },
        { title: "Sherlok Xolms", author: "Artur Konan Doyl", link: "#" }
    ];

    function checkPassword() {
        const pass = document.getElementById('password').value;
        if (pass === "bekha_01") {
            document.getElementById('login-box').style.display = 'none';
            document.getElementById('book-shelf').style.display = 'block';
            loadBooks();
        } else {
            document.getElementById('error-msg').style.display = 'block';
        }
    }

    function loadBooks() {
        const list = document.getElementById('book-list');
        books.forEach(book => {
            const card = `
                <div class="book-card">
                    <div class="book-info">
                        <h3>${book.title}</h3>
                        <p>${book.author}</p>
                    </div>
                    <button class="read-btn" onclick="window.location.href='${book.link}'">O'qish</button>
                </div>
            `;
            list.innerHTML += card;
        });
    }
</script>

</body>
</html>
