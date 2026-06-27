const password = document.getElementById("password");
const bar = document.getElementById("strengthBar");
const scoreText = document.getElementById("score");
const feedback = document.getElementById("feedback");
const statusBox = document.getElementById("status");

const len = document.getElementById("len");
const upper = document.getElementById("upper");
const lower = document.getElementById("lower");
const num = document.getElementById("num");
const sym = document.getElementById("sym");

password.addEventListener("input", () => {
  let v = password.value;
  let score = 0;

  let hasLen = v.length >= 8;
  let hasUpper = /[A-Z]/.test(v);
  let hasLower = /[a-z]/.test(v);
  let hasNum = /[0-9]/.test(v);
  let hasSym = /[@$!%*?&#]/.test(v);

  // checklist
  len.style.color = hasLen ? "#22c55e" : "#ff4d4d";
  upper.style.color = hasUpper ? "#22c55e" : "#ff4d4d";
  lower.style.color = hasLower ? "#22c55e" : "#ff4d4d";
  num.style.color = hasNum ? "#22c55e" : "#ff4d4d";
  sym.style.color = hasSym ? "#22c55e" : "#ff4d4d";

  len.textContent = hasLen ? "✔ At least 8 characters" : "❌ At least 8 characters";
  upper.textContent = hasUpper ? "✔ Uppercase letter" : "❌ Uppercase letter";
  lower.textContent = hasLower ? "✔ Lowercase letter" : "❌ Lowercase letter";
  num.textContent = hasNum ? "✔ Number" : "❌ Number";
  sym.textContent = hasSym ? "✔ Symbol" : "❌ Symbol";

  // score
  if (hasLen) score += 20;
  if (hasUpper) score += 20;
  if (hasLower) score += 15;
  if (hasNum) score += 20;
  if (hasSym) score += 25;

  bar.style.width = score + "%";
  scoreText.textContent = "Score: " + score + " / 100";

  // status
  if (v.length === 0) {
    statusBox.textContent = "NOT CHECKED";
    statusBox.style.background = "#555";
    feedback.textContent = "Waiting for input...";
    bar.style.background = "#1e293b";
    return;
  }

  if (score < 40) {
    statusBox.textContent = "WEAK ❌";
    statusBox.style.background = "#ff4d4d";
    bar.style.background = "#ff4d4d";
    feedback.textContent = "Weak password. Easily hackable.";
  }
  else if (score < 75) {
    statusBox.textContent = "MODERATE ⚠️";
    statusBox.style.background = "#facc15";
    bar.style.background = "#facc15";
    feedback.textContent = "Improve with symbols & length.";
  }
  else {
    statusBox.textContent = "STRONG 🔐";
    statusBox.style.background = "#22c55e";
    bar.style.background = "#22c55e";
    feedback.textContent = "Excellent security level.";
  }
});
