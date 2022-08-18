![jthread](https://raw.githubusercontent.com/StirlingLabs/jthread/main/doc/jthread.jpg)

[![CC BY 4.0][cc-by-shield]][cc-by] ![jthread](https://github.com/StirlingLabs/jthread/actions/workflows/integrate.yaml/badge.svg)

C++ class for a joining and cooperative interruptible thread (std::jthread) with stop_token helper:
- Reference implementation, cleaned up to be used as a polyfill on Mac until libc++ gets an official implementation
- Test suite
- Papers proposing it for the C++ standard
  -  http://wg21.link/p0660  (main proposal for C++20)
     - http://wg21.link/p1287  (initial proposal for stop callbacks, merged with p0660r7)
  -  http://wg21.link/p1869  (additional minor updates for C++20)

Main authors:  Nicolai Josuttis (http://www.josuttis.com/contact.html) and Lewis Baker

## ⚠️ Note

- Tests for _condition variable_ are not run in CI because this implementation does not work in a single-core environment. We recommend that you do not use CV from this repo until tests are run and passing. 
- The code is licensed under a Creative Commons [Attribution 4.0 International License][cc-by]. 

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg

## 🗒️ Contents

- <b>include/</b>
  - headers that can be included as an implementation in other projects (e.g. to polyfill Clang).
    - note attribution requirements under license
- <b>source/</b>
  - source code for the reference implementation and the test suite
    - to test the CV class extensions they are applied to a class condition_variable_any2
- <b>tex/</b>
  - final paper and proposed wording using C++ standard LaTeX style
    - to create the latest version:  `pdflatex std` 
- <b>doc/</b>
  - current and old documentations (all proposals P0660*.pdf)
