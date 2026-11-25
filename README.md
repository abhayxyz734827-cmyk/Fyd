# 🐻 Dashboard Bear EVO

**UDB1 + BR EVO MOD — PARALLEL MATCH VERSION**

## ✅ নতুন ফিচার
- **Parallel Matches**: এক অ্যাকাউন্টে একসাথে সর্বোচ্চ `MAX_PARALLEL_MATCHES_PER_ACC` (ডিফল্ট 10) UDP ম্যাচ চালানো যায়
- **TCP Gateway OFF after MATCH FOUND**: MATCH FOUND পেলে UDP চালু রাখা হয়, TCP বন্ধ করা হয়
- **Auto Reconnect**: TCP আবার কানেক্ট করে team flow + match start (শুধুমাত্র leader)
- **Max Limit Handling**: 10 ম্যাচ ফুল হলে TCP অন থাকে কিন্তু নতুন match start হয় না; স্লট ফ্রি হলে আবার চালু হয়
- **Editable**: Environment variable দিয়ে max parallel পরিবর্তন করা যায়

## ⚙️ BR EVO লুপ (Parallel)
1. TCP Connect + Auth
2. Exit Team → Create BR Evolution Team → Start Match (leader)
3. MATCH FOUND পেলে UDP join শুরু
4. TCP Gateway OFF (UDP চলতে থাকে)
5. আবার TCP Connect → Repeat (যদি active < max)
6. Max হলে TCP অন রেখে স্লট ফ্রি হওয়ার জন্য অপেক্ষা

## 🔧 Config
```bash
MAX_PARALLEL_MATCHES_PER_ACC=10   # ডিফল্ট 10, এডিট করা যায়
BR_EVO_DEBUG=0
```

## 🚀 Deploy
Railway/Render-এ আগের মতোই deploy করুন।
