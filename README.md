# -
스마트똑똑이저장소
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>기니피그 AI</title>
<style>
body{font-family:sans-serif;text-align:center;padding:20px}
button{padding:10px;margin:5px;border-radius:10px}
video{width:100%;border-radius:15px}
.box{padding:10px;margin:10px;border-radius:10px;background:#f0f0f0}
</style>
</head>
<body>

<h2>🐹 기니피그 현실 AI</h2>

<textarea id="input" placeholder="기니와 대화" style="width:100%;height:60px"></textarea>
<br>
<button onclick="talk()">💬 대화</button>
<button onclick="startCamera()">📷 카메라</button>

<br><br>
<video id="video" autoplay></video>
<br>
<button onclick="analyze()">🧠 행동 분석</button>

<div class="box" id="health">건강: 정상</div>
<div class="box" id="stress">스트레스: 낮음</div>
<div class="box" id="reply">안녕! 나는 기니 AI 🐹</div>

<script>
function talk(){
let t=document.getElementById("input").value
if(t.includes("밥")) reply.innerText="배고파! 채소 줘!"
else if(t.includes("놀")) reply.innerText="좋아! 놀자!"
else reply.innerText="옆에 있어줘 😊"
}

async function startCamera(){
let stream=await navigator.mediaDevices.getUserMedia({video:true})
video.srcObject=stream
}

function analyze(){
let list=[
["많이 움직임 → 건강 좋음","낮음"],
["구석에 숨음 → 스트레스 가능","중간"],
["움직임 거의 없음 → 체크 필요","높음"]
]
let r=list[Math.floor(Math.random()*3)]
reply.innerText=r[0]
stress.innerText="스트레스: "+r[1]
if(r[1]=="높음") health.innerText="건강: 검진 권장"
}
</script>

</body>
</html>
