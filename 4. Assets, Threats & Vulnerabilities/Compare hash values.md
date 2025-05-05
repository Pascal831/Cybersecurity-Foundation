# 🔐 Compare Hash Values – File Integrity Verification

## 🧠 Description

As a **security analyst**, one critical control we use to verify file integrity is **hashing**. A hash is a fixed-length string generated from a file’s contents, often referred to as a **hash value** or **digest**. 

Hashing helps ensure:
- Files have not been altered (intentionally or accidentally)
- Detection of tampered or malicious files
- Verification of software authenticity

> ⚠️ Even a single character change in a file will produce a completely different hash value.

---

## ⚙️ Generate and Compare Hashes

### 1. **View Files in Directory**
Use `ls` to list the files:
```bash
ls
```

Assume we have:
- `file1.txt`
- `file2.txt`

### 2. **Display File Contents**
```bash
cat file1.txt
cat file2.txt
```

📌 Both files may appear identical on visual inspection.

---

### 3. **Generate SHA256 Hash Values**
```bash
sha256sum file1.txt
sha256sum file2.txt
```

🔍 Despite visual similarity, **hash values differ**, confirming the files are not exact copies.

---

### 4. **Store Hashes in Separate Files**
```bash
sha256sum file1.txt > file1hash.txt
sha256sum file2.txt > file2hash.txt
```

### 5. **Inspect Hash Files**
```bash
cat file1hash.txt
cat file2hash.txt
```

---

### 6. **Compare Hash Files**
```bash
cmp file1hash.txt file2hash.txt
```

- If the files differ, `cmp` will output the first differing byte/line.
- If they’re the same, there will be no output (silent match).

---

## ✅ Summary

Although `file1.txt` and `file2.txt` **appeared identical**, their **hash values revealed a difference**. Hashing is an essential security technique for:
- File integrity checks
- Malware detection
- Software verification

> 🔐 Hashes do not reveal the contents of a file — they serve as a **digital fingerprint**.
