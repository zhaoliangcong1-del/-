index.html
<!doctype html>
<html lang="id">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Untukmu saja</title>
<style>
  body{
    margin:0;
    height:800vh;
    background:
      radial-gradient(ellipse at 30% 20%, rgba(255,190,225,0.22), transparent 60%),
      radial-gradient(ellipse at 70% 80%, rgba(170,200,255,0.22), transparent 60%),
      linear-gradient(135deg, #110d2b, #2a2560, #1a1838);
    font-family:"PingFang SC","Microsoft YaHei",sans-serif;
    color:#fafafa;
  }
  #wrap{
    position:fixed;
    inset:0;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:0 24px;
    text-align:center;
  }
  .txt{
    position:absolute;
    font-size:5.6vw;
    line-height:1.75;
    opacity:0;
    filter:blur(10px);
    max-width:88vw;
    text-shadow:0 2px 18px rgba(255,255,255,0.12);
  }
</style>
</head>
<body>

<div id="wrap">
  <div class="txt" id="t0">I LOVE YOU</div>
  <div class="txt" id="t1">Kita belum pernah bertemu</div>
  <div class="txt" id="t2">Lewat layar, lewat zona waktu</div>
  <div class="txt" id="t3">Tapi aku tulus</div>
  <div class="txt" id="t4">Tulus sampai</div>
  <div class="txt" id="t5">Aku sudah terbiasa dengan waktumu</div>
  <div class="txt" id="t6">Saat kamu bicara</div>
  <div class="txt" id="t7">Jarak terasa tidak sejauh itu</div>
  <div class="txt" id="t8">Rindu ingin bertemu kamu</div>
  <div class="txt" id="t9">Semakin nyata setiap hari</div>
  <div class="txt" id="t10">Saat kita bertemu nanti</div>
  <div class="txt" id="t11">Jantungku pasti berdebar</div>
  <div class="txt" id="t12">Tapi aku tidak takut</div>
  <div class="txt" id="t13">Karena aku sudah lama menyukaimu</div>
</div>

<script>
  const texts = [...document.querySelectorAll('.txt')];

  addEventListener('scroll', () => {
    let p = Math.min(scrollY / (innerHeight * 1.5), 1);
    let index = Math.floor(p * (texts.length - 1));
    let sub = (p * (texts.length - 1)) - index;

    texts.forEach((t, i) => {
      let opacity = 0, blur = 10, y = 40;

      if (i === index) {
        opacity = 1 - sub;
        blur = sub * 10;
        y = sub * 40;
      }
      if (i === index + 1) {
        opacity = sub;
        blur = (1 - sub) * 10;
        y = (sub - 1) * 40;
      }

      t.style.opacity = opacity;
      t.style.filter = `blur(${blur}px)`;
      t.style.transform = `translateY(${y}px)`;
    });
  });

  texts[0].style.opacity = 1;
  texts[0].style.filter = 'blur(0px)';
</script>
</body>
</html>