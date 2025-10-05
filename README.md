My favorite dream.<br>
                              Tumhare liye tumhara ego/ self respect mayne rakhta hai.. lekin tumne apna self respect barkaraar rakha... Yaad hai ek waqt tha tumne hi kha tha ki jab maine usko birthday wish Kiya tha to tumne bola tha ki apni self respect jaruri hoti hai. Or maine bola tha ki pyar or dosti me self respect ki koi jagah nhi hoti.. lekin shayad mai galat tha.. meri life me to hai.. lekin mai ye bhool gya tha ki dusro ki life me unke liye kya mayne hai..  khair jaane do.. tumko waqt chahiye to le lo.. mai nhi aaunga tumko disturb karne..  mujhe tumhari photos ko dekh tumhare diye gaye letters ko padh .. tumhare favourite gane sun ke mai din gujarna manjur hai lekin meri expectations se khud ko roj roj   hurt karna bilkul manzoor nhi.. maine jab dekha tumne msg seen kar ke bhi reply nhi Diya to mai kya samjhu.. tum bas mere se isliye baat ki kyuki tumko lga ki mai depression me hu..  see mai jaisa bhi hu thik bekar.. mere pass agr aao to purani wali ya to dost ya fir meri bhutki banke aana..
Ye hamdardi jante ke liye maat aaya karna.. mujhe sabse jyada bura hamdardi jtane walo se lagta hai.. mai ab jaa rha hu to ab iska koi mtlb to nhi Banta but still maine ye kha .. or ha tumko boards tak ka time chahiye tha maine diya.. tumahara board ke baad mai fir ek baar aaunga and uske baad tumhara jo decision hoga wo mera final hoga.. kyuki tum to bin btaye chali jaati ho pareshan mai hota hu tumko lekar.. or ab roj roj ye soch kar ki aab tumhare msg aaye ga ab ayega lekin msg nhi aata .. ab mai apni roj roj ankhe nam nhi kar sakta .. it's better ki mai yha se Chala jau.. kam se kaam is loop me fasa rahunga ki tum khush ho.. apne padhai pe focus kar rhi hogi.. jo bhi ek wajah tha wo bhi ab nhi rha.. tumne apne letter me likha tha ki kabhi bhi kisi pe burden nhi samjhu.. dekho aaj mai tumpe hi burden baan gya hu.. lekin ab or nhi.. maaf karna.. mujhe maine bahut jhel liya ,so pls.. ab or nhi sha jaa rha.. mai tumhara intezar kar lunga jaise 4 mahine nikal gaye waise hi 8 mhine
AB MERI NOTIFICATION LIST ME TUMHARE ALAWA OR KOI MSG NHI HOGA.. AGR HOGA TO SIRF TUMAHRA NHI TO KISI KA BHI NHI....TAB TAK KE LIYE MAI TUMHARE BHAGWAN JI SE YEHI PRATHNA KARUNGA KI WO TUMKO HAMESHA KHUSH RAKHE.. UNKI KRIPA TUMNE SDA BNI RHE.. TUMKO HIMMAT DE TUMHARI PROBLEM SE LADNE KE LIYE✨🙌.. I LOVE U 🥹💖      ॐ नमो भगवते वासुदेवाय नमः 🪷ki meri BHUTKI KA KHYAL RAKHNA 🧿💫.. 
AAJ akhri baar....
 Good night ✨,,
Sweet dreams 💫
GOOD BYE 🥺</p>
            </div>
        </div>

        <div class="audio-controls">
            <p>🎧 I recorded this just for you… press play:</p>
            <audio id="personalMessage">
                <source src="s1.mp3" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
            <!-- Play Button for Audio -->
            <button id="playButton" onclick="playAudio()">▶️ Play My Message</button>
        </div>

        <div id="secretMessage">
             Shhhuuu🤫 .. EK AAKHRI SURPRISE.. Kahi bhi 5 bar tap kijiye🙌🫶...
        </div>

        <p style="margin-top: 30px; font-size: 1.4rem;">
            I love you more than yesterday… but less than tomorrow. 😘💖
        </p>

        <!-- CIRCULAR GIF SECTION -->
        <div class="gif-section">
            <img src="https://i.imghippo.com/files/uft5421Ho.gif" alt="Love You!">
        </div>
    </div>

    <script>
        let currentScreen = 1;
        let tapCount = 0;

        // Show current date
        document.getElementById('currentDate').innerText = new Date().toLocaleDateString('en-US', {
            weekday: 'long',
            year: 'numeric',
            month: 'long',
            day: 'numeric'
        });

        function nextScreen(from) {
            document.getElementById(`screen${from}`).classList.remove('active');
            document.getElementById(`screen${from + 1}`).classList.add('active');
            currentScreen = from + 1;

            // Start background music on first real step
            if (from === 1 && currentScreen === 2) {
                const bgMusic = document.getElementById('bgMusic');
                bgMusic.volume = 0.2; // Soft background volume
                bgMusic.play().catch(e => {
                    // If blocked by browser, ask user to tap
                    document.body.addEventListener('click', () => {
                        bgMusic.play();
                    }, { once: true });
                });
            }

            if (currentScreen === 2) {
                createFloatingHearts();
                startCountdownTimer();
            } else if (currentScreen === 3) {
                // Gentle confetti
                for (let i = 0; i < 20; i++) {
                    setTimeout(() => {
                        createConfetti();
                    }, i * 100);
                }
            } else if (currentScreen === 6) {
                // Do NOT call showSecretHint here - it will trigger after voice message ends
            }
        }

        function startCountdownTimer() {
            let count = 5;
            const timerEl = document.getElementById('countdown-timer');
            const interval = setInterval(() => {
                count--;
                timerEl.innerText = count;
                if (count <= 0) {
                    clearInterval(interval);
                    nextScreen(2); // Directly transition without delay
                }
            }, 1000);
        }

        function revealBox() {
            const box = document.getElementById('blockBox');
            box.innerHTML = "💝";
            box.style.background = "#ff6b6b";
            box.style.transform = "scale(1.5) rotate(720deg)";
setTimeout(() => {
                nextScreen(5);
            }, 800);
        }

        function launchFireworks() {
            // Fade out background music
            const bgMusic = document.getElementById('bgMusic');
            let vol = bgMusic.volume;
            const fade = setInterval(() => {
                vol -= 0.05;
                if (vol <= 0.05) {
                    clearInterval(fade);
                    bgMusic.volume = 0.05;
                } else {
                    bgMusic.volume = vol;
                }
            }, 100);

            // Launch fireworks/confetti
            for (let i = 0; i < 30; i++) {
                setTimeout(() => createFirework(), i * 100);
            }
            for (let i = 0; i < 100; i++) {
                setTimeout(() => createConfetti(), i * 30);
            }
            if (navigator.vibrate) navigator.vibrate([100, 50, 100]);
        }

        function playAudio() {
            const audio = document.getElementById('personalMessage');
            audio.play();
            launchFireworks();
        }

        function createFirework() {
            const firework = document.createElement('div');
            firework.classList.add('firework');
            firework.style.left = Math.random() * 100 + 'vw';
            firework.style.top = Math.random() * 100 + 'vh';
firework.style.backgroundColor = ['#ff6b6b', '#ffd93d', '#37c8ff', '#a8edea'][Math.floor(Math.random() * 4)];
            document.body.appendChild(firework);
            setTimeout(() => firework.remove(), 1000);
        }

        function createConfetti() {
            const confetti = document.createElement('div');
            confetti.classList.add('confetti');
            confetti.style.left = Math.random() * 100 + 'vw';
            confetti.style.backgroundColor = ['#ff6b6b', '#feca57', '#1dd1a1', '#ff9ff3', '#54a0ff'][Math.floor(Math.random() * 5)];
            document.body.appendChild(confetti);
            setTimeout(() => confetti.remove(), 3000);
        }

        function createFloatingHearts() {
            for (let i = 0; i < 25; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.classList.add('floating-heart');
                    heart.innerHTML = ['❤️', '💕', '💖', '💗'][Math.floor(Math.random() * 4)];
                    heart.style.left = Math.random() * 100 + 'vw';
                    heart.style.animationDelay = Math.random() * 5 + 's';
                    document.body.appendChild(heart);
                    setTimeout(() => heart.remove(), 7000);
                }, i * 250);
            }
        }

        function showSecretHint() {
            const secretMessage = document.getElementById('secretMessage');
            secretMessage.style.display = 'block';
            secretMessage.style.top = '0';
            secretMessage.style.transform = 'translateX(-50%)';
        }

        function handleTap() {
            if (currentScreen !== 6) return;
tapCount++;
            if (tapCount >= 5) {
                tapCount = 0;
                revealSecretMessage();
            }
        }

        function revealSecretMessage() {
            const secretDiv = document.createElement('div');
            secretDiv.innerHTML = `
                <div style="
                    position: fixed;
                    top: 0;
                    left: 50%;
                    transform: translateX(-50%);
                    background: white;
                    color: #ff6b6b;
                    padding: 30px;
                    border-radius: 25px;
                    box-shadow: 0 10px 40px rgba(0,0,0,0.3);
                    z-index: 9999;
                    max-width: 90%;
                    text-align: center;
                    animation: fadeIn 0.5s;
                ">
                    <h2>💌 My Secret to You 💌</h2>
                    <p style="font-size: 1.3rem; margin: 20px 0;">
                        Even when we’re apart, you’re my favorite thought.<br>
                        My favorite dream.<br>
                        My favorite person to miss.<br><br>
                        I’m counting every second until I see you again.<br>
                        And when I do?<br>
                        First: Hug. Second: Kiss. Third: Never letting go.<br><br>
                        I love you beyond words, beyond distance, beyond time.<br>
                        Forever yours.
                    </p>
                    <button onclick="this.parentElement.remove()" style="
                        background: #ff6b6b;
                        color: white;
                        border: none;
padding: 12px 30px;
                        border-radius: 50px;
                        font-size: 1.1rem;
                        cursor: pointer;
                        margin-top: 20px;
                    ">Close</button>
                </div>
            `;
            document.body.appendChild(secretDiv);
        }

        // Show caption + zoom + heart burst
        function showCaption(num) {
            // Reset all
            document.querySelectorAll('.gallery-item').forEach(item => {
                item.classList.remove('active');
            });
            document.querySelectorAll('.caption').forEach(el => el.style.display = 'none');

            // Show selected caption
            const item = document.querySelector(`.gallery-item:nth-child(${num})`);
            const caption = document.getElementById(`caption${num}`);

            if (item && caption) {
                item.classList.add('active');

                // Create heart burst at tap position
                const rect = item.getBoundingClientRect();
                const heart = document.createElement('div');
                heart.classList.add('heart-burst');
                heart.innerHTML = '💖';
                heart.style.left = (rect.left + rect.width/2) + 'px';
                heart.style.top = (rect.top + rect.height/2) + 'px';
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 800);

                // Show caption
                caption.style.display = 'block';
                caption.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
// Auto-hide after 8 seconds (optional)
                setTimeout(() => {
                    caption.style.display = 'none';
                    item.classList.remove('active');
                }, 8000);
            }
        }

        // Trigger secret message after voice message ends
        document.getElementById('personalMessage').addEventListener('ended', showSecretHint);
    </script>

</body>
</html>
