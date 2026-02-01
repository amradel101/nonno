<div class="container">
    <img id="sticker" src="https://media.giphy.com/media/t8xgPfC5oNIRMrNooe/giphy.gif" alt="Panda">
    <h1 id="question">Will you be my Valentine, MERVAT? ❤️</h1>
    <div id="message"></div>
    <div class="buttons">
        <button id="yesBtn">Yes</button>
        <button id="noBtn">No</button>
    </div>
</div>

<script>
    const noBtn = document.getElementById('noBtn');
    const yesBtn = document.getElementById('yesBtn');
    const message = document.getElementById('message');
    const sticker = document.getElementById('sticker');
    const question = document.getElementById('question');

    // الحيلة هنا: تحميل الصورة التانية في الخلفية أول ما الصفحة تفتح
    const finalGifUrl = "https://media.giphy.com/media/1JmGiBtqTuehfYxuy9/giphy.gif";
    const preloader = new Image();
    preloader.src = finalGifUrl;

    // لما تقف على Yes
    yesBtn.onmouseover = () => { message.innerText = "press here please 🥺✨"; };
    yesBtn.onmouseout = () => { message.innerText = ""; };

    // لما تقف على No
    noBtn.addEventListener('mouseover', () => {
        message.innerText = "don't press here its dangerous! 😂";
        noBtn.style.position = 'fixed';
        const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
        const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
        noBtn.style.left = x + 'px';
        noBtn.style.top = y + 'px';
    });

    // تنفيذ أمر التغيير
    yesBtn.onclick = function() {
        // تغيير النص
        question.innerText = "Yay! I Love You! ❤️";
        message.innerText = "i love you MERVAT! 🥰";
        
        // تغيير الصورة باستخدام الرابط اللي حملناه مسبقاً
        sticker.src = preloader.src;
        
        // إخفاء زرار No
        noBtn.style.display = 'none';
    };
</script>
