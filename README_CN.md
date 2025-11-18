# docxlatex - 增强版

本仓库是 [docxlatex](https://github.com/hrushikeshrv/docxlatex) 的 fork 版本，添加了 Unicode 数学符号到 LaTeX 命令的自动转换功能。

## 新增功能

### Unicode 符号自动转换

在 OMML (Office MathML) 公式解析过程中，自动将 Unicode 数学符号转换为对应的 LaTeX 命令。

**支持的符号类型**：
- **希腊字母**（小写）: α→\alpha, β→\beta, γ→\gamma, δ→\delta, θ→\theta, ω→\omega 等
- **希腊字母**（大写）: Γ→\Gamma, Δ→\Delta, Θ→\Theta, Σ→\Sigma, Ω→\Omega 等
- **数学运算符**: ∂→\partial, ∇→\nabla, ∞→\infty, ∑→\sum, ∏→\prod
- **关系符号**: ≈→\approx, ≠→\neq, ≡→\equiv, ≤→\leq, ≥→\geq, ∈→\in
- **箭头符号**: ↑→\uparrow, ↓→\downarrow
- **集合运算**: ∪→\cup, ∩→\cap, ∅→\emptyset, ∀→\forall, ∃→\exists
- **逻辑符号**: ∧→\wedge, ∨→\vee, ¬→\neg
- **其他常用符号**: ±→\pm, ×→\times, ÷→\div, ·→\cdot 等

### 技术特性

- **字符级处理**: 逐字符扫描和替换，确保连续的 Unicode 符号都能正确转换
- **自动空格插入**: LaTeX 命令后自动添加空格，防止命令与后续文本粘连（如 `\partial h` 而非 `\partialh`）
- **完整覆盖**: 支持 80+ 个常用数学 Unicode 符号

### 修改的文件

- `docxlatex/parser/ommlparser.py` - 在 `parse_t()` 方法中添加 Unicode 到 LaTeX 的映射表和转换逻辑

## 示例

**输入** (Word 文档中的公式):
```
∂p/∂θ + ω∇²φ = 0
```

**输出** (LaTeX):
```latex
\partial p/\partial \theta + \omega \nabla ^2 \varphi = 0
```

## 安装

从 GitHub 安装：

```bash
pip install git+https://github.com/shiyuanpei/docxlatex.git@main
```

## 用途

本增强版主要用于 [markitdown](https://github.com/shiyuanpei/markitdown) 项目，
实现 Office 文档到 Markdown 的高质量转换，特别是包含数学公式的技术文档。

## 原始项目

原始 docxlatex 项目: https://github.com/hrushikeshrv/docxlatex

## 许可证

与原项目保持一致的开源许可证。
