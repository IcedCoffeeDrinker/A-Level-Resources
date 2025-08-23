# 2.4 Practice & Exam-style

## 2.02

- Buffer: 1 MiB
- Low-water mark: 100 KiB
- High-water mark: 900 KiB
- Input: 1 Mbps ≈ 122.07 KiBps
- Output: 300 kbps ≈ 36.62 KiBps
- Initial: 100 KiB

---

$$
1 \text{ Mbps} = 1000 \text{ kbps} = 125 \text{ KBps}
$$
$$
\frac{125 \times 1000}{1024} \approx 122.07 \text{ KiBps}
$$
$$
300 \text{ kbps} = \frac{300 \times 1000}{8 \times 1024} \approx 36.62 \text{ KiBps}
$$

---

$$
\text{Buffer} = f(t) = 100 + (122.07 - 36.62)t
$$
- $$f(4) = 441.8 \text{ KiB}$$
- $$f(6) = 612.7 \text{ KiB}$$
- $$f(8) = 783.6 \text{ KiB}$$
- $$f(10) = 954.5 \text{ KiB}$$
- $$f(12) = 1125.4 \text{ KiB}$$
(would stop before, not correct)

---

$$
900 = 100 + (122.07 - 36.62)t
$$
$$
t = \frac{800}{85.45}
$$
$$
t = 9.362 \text{ s}
$$

after t = 9.362s
$$
f(x) = 900 - 36.62(t-9.362)
$$
- $$f(10) = 876.64 \text{ KiB}$$
- $$f(12) = 803.40 \text{ kiB}$$

$$
0 = 900 - 36.62t
$$
$$
t = \frac{-900}{-36.62} = 24.58 \text{ s}
$$

## Examstyle question #3
Describe: 6 Points _not explain. 1 point for every example_

- He would have to ensure a stable internet connection so he is able to recieve data at all. ((L) not listed)
- He should have a propperly sized buffer that is able to compensate for an unstable bit rate. ✔️
- He should have enough bandwith so that the bit rate surpasses that of his stream, which is necessary for streaming. ✔️
- He should make sure his end-device is capable of fast download speeds, as the connection will only be as fast as the weekest link in the chain. (not listed so (L))

not a good score :(
$$
\frac{2}{6} \text{ to } \frac{4}{6}
$$

_we have to improve understanding of operators;_
_e.g. explain, describe, etc_