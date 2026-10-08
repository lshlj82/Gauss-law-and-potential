# Gauss's Law and Electric Potential

This is an interactive, browser-based demo of Gauss's law and electric potential. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 전기다발, 가우스 법칙, 도체, 대칭성을 이용한 전기장 계산, 껍질 이론, 전기 퍼텐셜과 퍼텐셜 에너지, 등퍼텐셜면, 쌍극자와 연속 전하 분포의 퍼텐셜, 전하계의 에너지, 고립된 도체를 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `gauss-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `gauss-en.html` | American English version |
| `gauss-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar. Equations use real fraction bars and radical signs. For example, $V = \frac{\sigma}{2\varepsilon_0}\left(\sqrt{z^2+R^2}-z\right)$ is displayed as typeset math, not as `sqrt(...)`.

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/gauss-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/gauss-en.html` or `.../gauss-ko.html`.

These pages can share a repository with the companion demos: DC circuits (`circuits-*.html`), RC circuits (`rc-*.html`), magnetism (`magnetism-*.html`), induction and AC (`induction-*.html`), and Maxwell's equations and light (`maxwell-*.html`). The file names don't collide.

## What's inside

The twelve sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Electric flux:** A small patch sits in a uniform field, and you can tilt it. The page shows $\Delta\Phi = E\,\Delta A\cos\theta$, highlights the field lines that pass through the patch, and says whether the flux is outward or inward. A side note works out the cylinder example, where the net flux is zero.
2. **Gauss's law:** You can drag a spherical Gaussian surface among two charges, or use the presets that match the four surfaces in the notes. The page integrates $\oint \vec E\cdot d\vec A$ numerically over the full 3D sphere and compares the result with $q_\text{enc}/\varepsilon_0$.
3. **Coulomb from Gauss:** A Gaussian sphere surrounds a point charge. As the radius changes, the flux stays at $q/\varepsilon_0$ while $E$ falls as $1/r^2$. A "double r" button shows $E$ dropping to $E/4$.
4. **Conductors:** A conducting sphere sits in a uniform external field. The induced surface charges are drawn, field lines meet the surface at right angles, and the field inside is $\vec E = 0$.
5. **Planes and lines:** This section covers a nonconducting sheet ($E=\sigma/2\varepsilon_0$), a conducting plate ($E=\sigma/\varepsilon_0$), and a line of charge ($E=\lambda/2\pi\varepsilon_0 r$). Each comes with its pillbox or cylindrical Gaussian surface and a graph of $E$ against distance.
6. **Shell theorems:** This section compares a thin shell with a uniformly charged ball. It shows the enclosed charge and $E(r)$, including the field inside the ball, $E = qr/4\pi\varepsilon_0 R^3$.
7. **Electric potential:** A proton or an electron is released between two charged plates. Energy bars show $U$ turning into $K$ according to $\Delta K = -q\,\Delta V$, with values in eV and joules and the final speed.
8. **Equipotentials:** You can drag up to three charges and a probe point P. The page draws equipotential contours and field arrows, and checks Coulomb's-law $\vec E$ against the numerical $-\nabla V$.
9. **Point charge and dipole:** For a point charge, the page compares $V(r)$ with $E(r)$. For a dipole, it compares the exact potential with the approximation $p\cos\theta/4\pi\varepsilon_0 r^2$ and shows the percentage error as $r/d$ grows.
10. **Continuous charge:** This section handles a rod and a disk. The closed-form $V$ is compared with a direct sum over 2000 pieces $dq$, and for the disk, $E_z$ is also compared with the numerical $-\partial V/\partial z$.
11. **Energy of a system of charges:** You can drag three charges. Each pair is labeled with its energy $U_{ij}$, colored by sign, and the page shows the total energy, which is the work needed to assemble the charges.
12. **Isolated conductors:** Two spheres are joined by a wire. They reach the same potential, so $q_1:q_2 = r_1:r_2$ and $\sigma_1:\sigma_2 = 1/r_1 : 1/r_2$. The page also graphs $V(r)$ and $E(r)$ for a charged conducting sphere, and the section ends with a summary of $\vec E$ (a vector field) and $V$ (a scalar field).

## Notes on the model

- **Units:** Charges are in nC, distances in cm, and all results are in SI units, using $k = 8.9875\times10^9\ \text{N·m}^2/\text{C}^2$ and $\varepsilon_0 = 8.854\times10^{-12}\ \text{C}^2/(\text{N·m}^2)$.
- **2D pictures, 3D physics:** The drawings are 2D cross-sections. The fields and fluxes are computed for real 3D point charges.
- **Sphere in a field:** The conductor in section 4 uses the exact solution for a conducting sphere in a uniform field.
- **Light and dark:** The pages follow the system's light or dark setting, and a sun/moon button in the top-right corner switches by hand, and the choice is remembered across pages.
- **Reduced motion:** Under `prefers-reduced-motion`, the decorative header animation stays still.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
