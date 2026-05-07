<!DOCTYPE html>
<html>
<head>
    <title>AI Support Bot</title>
</head>
<body>
    <h2>AI Support Assistant</h2>
    <input id="query" placeholder="Ask a question" />
    <button onclick="askBot()">Ask</button>

    <p id="response"></p>

    <script>
        async function askBot() {
            const q = document.getElementById("query").value;
            const res = await fetch(`/test?q=${encodeURIComponent(q)}`);
            const data = await res.json();
            document.getElementById("response").innerText = data.answer;
        }
    </script>
</body>
</html>
