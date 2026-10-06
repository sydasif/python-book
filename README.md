# [Network Automation?](https://python-automation-book.readthedocs.io/en/latest/)

Network automation is the process of automating a computer network's configuration, management and operations. The tasks usually done by the network or system administrator can be automated using several tools and technologies.

Scripting languages are widely used by Network and System administrators for automating tasks. This saves time, and effort and thereby reduces human errors as well. Among the automation tools, Python and Ansible are the most popular ones. With Software Defined Networking (SDN) in picture, knowing any of these programming languages is vital for the future of administering the network and systems.


---

**Hosted version:** <https://python-automation-book.readthedocs.io/en/latest/> — Read the Docs rebuilds the HTML, PDF and ePub automatically on every push (see `.readthedocs.yaml`).

## Building the PDF book locally

### Prerequisites

System packages (TeX Live for LaTeX, `latexmk` to drive it):

```bash
sudo apt-get update
sudo apt-get install texlive-xetex texlive-fonts-recommended texlive-plain-generic
sudo apt install latexmk
```

Python environment (Sphinx, MyST Markdown parser, book theme):

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

> Note: `pandoc` is **not** required for this build. The pipeline is
> `sphinx-build` (MyST parses the Markdown natively) → `latexmk` → `pdflatex`.

### Build

```bash
source venv/bin/activate
cd docs
make latexpdf
```

Output: `docs/build/latex/pythonfornetworkengineers.pdf`
(the filename is derived from the `project` name in `docs/source/conf.py`;
note this project's Makefile uses `build/` as its build directory, which is
already covered by `.gitignore`).

### HTML preview

```bash
cd docs
make html          # open docs/build/html/index.html
```

### Unicode glyphs in code blocks

Directory trees in the chapters use box-drawing characters (`─`, `├`, `└`).
pdflatex only knows these because of the `latex_elements` preamble in
`docs/source/conf.py`, which maps each one to a LaTeX equivalent. **If you add
a new non-ASCII character to a code block, add a matching
`\DeclareUnicodeCharacter{...}{...}` line there**, otherwise the PDF build
fails with `LaTeX Error: Unicode character ... not set up for use with LaTeX`.
