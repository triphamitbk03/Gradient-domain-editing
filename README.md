# 🌈 Gradient-Domain Image Editing  
**Poisson Blending • Mixed Gradient • Laplacian Pyramid**

This repository implements gradient-domain image fusion techniques including **Poisson Image Editing**, **Mixed Gradient Blending**, and **Laplacian Pyramid Blending**.  
It also includes **Case A/B experiments**, **Background Smooth tests**, and reproducible notebooks.

---

## 📂 Project Structure

```
📦 Gradient-domain-editing
 ┣ 📜 GradientDomainFusion.ipynb      # Poisson + Mixed Gradient + experiments
 ┣ 📜 mixedGradient.ipynb             # Full Mixed Gradient implementation
 ┣ 📁 samples/                        # Input images & masks
 ┣ 📁 results/                        # Output blended images
 ┗ 📜 README.md
```

---

## ✨ Overview

### 🔶 Poisson Image Editing  
Solves the gradient-domain reconstruction equation:

\[
\nabla^2 v = \nabla \cdot g
\]

- Seamless cloning  
- Smooth transitions  
- Uses sparse linear solver (`spsolve`)

### 🔶 Mixed Gradient Blending  
Chooses stronger gradient between source & target:

\[
g = \begin{cases}
\nabla s, & |\nabla s| > |\nabla t| \\
\nabla t, & \text{otherwise}
\end{cases}
\]

- Preserves strong edges  
- Retains background texture  
- Reduces flattening artifacts

### 🔶 Laplacian Pyramid Blending  
Multi-scale blending for smooth color transitions:

- Handles color mismatch  
- Good for soft masks  
- Works well for natural scenes

---

## 🔬 Experiments (Case A & Case B)

### **Case A – Background Smooth**
- Ideal for Poisson blending  
- Smooth seamless edges  
- Mixed Gradient also works well

### **Case B – Textured / Strong Background**
- Poisson may flatten texture  
- Mixed Gradient preserves texture best  
- Laplacian Pyramid smooth but may blur edges  

Outputs stored in:

```
results/caseA/
results/caseB/
```

---

## 🛠 Installation

```bash
git clone https://github.com/triphamitbk03/Gradient-domain-editing.git
cd Gradient-domain-editing
pip install -r requirements.txt
```

Or install manually:

```bash
pip install numpy scipy opencv-python matplotlib pillow
```

---

## 🚀 Usage

### Run notebooks:

```bash
jupyter notebook
```

Open:

- `GradientDomainFusion.ipynb`
- `mixedGradient.ipynb`

Modify file paths to test your own images.

---

## 🖼 Results Example

| Method | Result |
|--------|--------|
| Poisson Blending | *(example result)* |
| Mixed Gradient | *(example result)* |
| Laplacian Pyramid | *(example result)* |

Add your output images inside `results/`.

---

## 📚 References

```
[1] P. Pérez, M. Gangnet, A. Blake.
    "Poisson Image Editing".
    ACM SIGGRAPH 2003.

[2] A. Gooch, S. Olsen, J. Tumblin, B. Gooch.
    "Color2Gray: Salience-Preserving Color Removal".
    ACM SIGGRAPH 2005.
```

---

## ✍️ Author
**Tri Pham — Ho Chi Minh City University of Technology (HCMUT)**

---

## 📝 License
MIT License.
