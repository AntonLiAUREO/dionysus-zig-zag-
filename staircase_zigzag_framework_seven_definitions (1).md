# A Staircase–Zigzag Framework over Rips Blowups

## Standing assumptions and notation

- Work over a fixed field $\Bbbk$. All chain and homology groups $H_k(-)$ are taken with $\Bbbk$-coefficients.
- $X$ is a finite metric space (e.g., a finite point cloud with metric $d$). For $\alpha\ge0$, $\mathrm{VR}_\alpha(X)$ denotes the **Vietoris–Rips complex** on $X$ at scale $\alpha$: a simplex on $S\subseteq X$ is present iff every pair in $S$ has distance $\le\alpha$.
- Fix a **cover** $\mathcal U=\{X^i\}_{i\in[m]}$ of $X$ (with $[m]:=\{1,\dots,m\}$). For nonempty $J\subseteq[m]$, write $X^J:=\bigcap_{i\in J}X^i$.
- For each $\alpha$, set
  $$
  K_\alpha:=\mathrm{VR}_\alpha(X), \qquad K_\alpha^J:=\mathrm{VR}_\alpha(X^J)\subseteq K_\alpha,
  $$
  where $K_\alpha^J$ is the induced subcomplex on the vertex set $X^J$.
- Let $\Delta^{m-1}$ be the standard $(m-1)$-simplex with vertices $\{e_1,\dots,e_m\}$; for $J\subseteq[m]$, $\Delta^J$ denotes the face spanned by $\{e_i: i\in J\}$.
- **Chain-level convention:** We do not fix a prism triangulation. All blocks $K_{α}^J × Δ^J$ are handled at the chain level using generators $(σ, J)$ and the standard product boundary (X-part plus $Δ$-part). Over $ℤ_2$ the signs vanish. We grade blowup cells by degree $\deg(\sigma,J):=\dim\sigma+|J|-1$.
- Let $\alpha_0<\alpha_1<\cdots<\alpha_L$ be a finite **scale grid**. (In applications one often chooses it to include Rips critical values; not required for the definitions.)

---

## Definition 1 (Rips blowup at scale α — chain-level model)

For $\alpha\ge0$ the **(simplicial) blowup complex** of $K_\alpha$ with respect to $\mathcal U$ is

$$
B_\alpha := K_\alpha^{\mathcal U}
= \bigcup_{\varnothing\ne J\subseteq[m]} K_\alpha^J \times \Delta^J
\subseteq K_\alpha\times\Delta^{m-1},
$$

We work with the chain-level blowup complex $C_*(B_{α})$ (no explicit prism triangulation). $π_X$ and $π_Δ$ denote the evident projections; the chain-level model is chain-equivalent to any simplicial prism triangulation.

**Remarks.** (1) In many standard situations $π_X$ is a homotopy equivalence, so $H_*(B_\alpha)\cong H_*(K_\alpha)$ while $\pi_\Delta$ records where in the cover a class is located. (2) Using the induced subcomplex $K_\alpha^J$ enforces that a simplex is supported inside $X^J$ rather than merely intersecting it.

---

## Definition 2 (Activation thresholds and activated blowup)

Fix an integer $k_{\max}\ge0$ (highest homological degree of interest). For each nonempty $J\subseteq[m]$ define the **activation threshold**

$$
 a_J := \inf\Big\{\alpha\ge0:\ K_\alpha^J\ \text{contains a nondegenerate $k$-simplex for some }0\le k\le k_{\max}\Big\}.
$$

For grid index $j$, the **activated index family** and the \*\*activated blowup at layer \*\***$j$** are

$$
\mathsf{Act}_j := \{J\subseteq[m],\ J\ne\varnothing:\ \alpha_j\ge a_J\},
\qquad
B_j^{\mathrm{act}} := \bigcup_{J\in\mathsf{Act}_j} K_{\alpha_j}^J\times\Delta^J \subseteq B_{\alpha_j}.
$$

**Remarks.** (1) When $\alpha$ is very small, many $K_\alpha^J$ are discrete sets of vertices; delaying their participation until the first edge/face appears avoids vacuous intra-layer steps. (2) If degree-$0$ information should be treated differently, one may use reduced homology or declare $a_J=0$ for $H_0$ while keeping the above rule for $k\ge1$.

---

Let $\mathcal P_j$ be the set of blowup **cells** $(\sigma,J)\subset B_j^{\mathrm{act}}$. Define a partial order on $\mathcal P_j$ by

$$
(\sigma,J)\ \prec\ (\sigma',J')
\quad\Longleftrightarrow\quad
\big(|J|,\ \dim\sigma\big)\ \text{is lexicographically smaller than}\ \big(|J'|,\ \dim\sigma'\big).
$$

Fix a linear extension of $\prec$, and let

$$
F_j(0)\ \subset\ F_j(1)\ \subset\ \cdots\ \subset\ F_j(T_j)=B_j^{\mathrm{act}}
$$

be the induced **intra-layer filtration** obtained by adding one (or any finite block of equal-rank) element(s) of $\mathcal P_j$ at a time in the chosen order.

**Remarks.** (1) This is the blowup analogue of the localized-homology filtration: sort by the “cover depth” $|J|$, then by simplex dimension. (2) Any deterministic tie-breaker among simplices with the same $(|J|,\dim\sigma)$ is acceptable; different choices are related by elementary contiguity and do not affect the well-posedness of the zigzag.

---

## Definition 4 (Glue and peel intra-layer zigzags)

For layer $j$ there are two canonical ways to traverse the filtration $\{F_j(t)\}_{t=0}^{T_j}$ as a zigzag of **inclusions**:

- The **glue zigzag** is the forward chain of inclusions
  $$
  \mathcal Z_j^{\mathrm{glue}}:\quad
  F_j(0)\ \hookrightarrow\ F_j(1)\ \hookrightarrow\ \cdots\ \hookrightarrow\ F_j(T_j)=B_j^{\mathrm{act}}.
  $$
- The **peel zigzag** is the reversed inclusion chain (all arrows oriented the same way)
  $$
  \mathcal Z_j^{\mathrm{peel}}:\quad
  F_j(T_j) \hookleftarrow F_j(T_j-1) \hookleftarrow F_j(T_j-2) \hookleftarrow \cdots \hookleftarrow F_j(0),
  $$
  where each arrow is an inclusion of one filtration term into the next object in the zigzag.

A **layer schedule** is the choice $s_j\in\{\mathrm{glue},\mathrm{peel}\}$ for each $j$.

**Remarks.** (1) Within a single peel segment we use a same‑direction chain of inclusions: since $F_j(T_j)\supset\cdots\supset F_j(0)$ and we list from large to small, all arrows are leftward ($\hookleftarrow$). (2) Zigzag “alternation” arises only when concatenating segments via the bridges in Definition 5 or when interleaving glue and peel across layers; all morphisms remain inclusions.

---

## Definition 5 (Inter-layer bridges)

To connect consecutive layers $j$ and $j+1$ at scales $\alpha_j<\alpha_{j+1}$, introduce an intermediate **bridge** complex built from $B_j^{\mathrm{act}}$ and $B_{j+1}^{\mathrm{act}}$:

- The **intersection bridge**
  $$
  M_j := B_j^{\mathrm{act}}\ \cap\ B_{j+1}^{\mathrm{act}},
  \qquad
  B_j^{\mathrm{act}}\ \hookleftarrow\ M_j\ \hookrightarrow\ B_{j+1}^{\mathrm{act}};
  $$
- or the **union bridge**
  $$
  N_j := B_j^{\mathrm{act}}\ \cup\ B_{j+1}^{\mathrm{act}},
  \qquad
  B_j^{\mathrm{act}}\ \hookrightarrow\ N_j\ \hookleftarrow\ B_{j+1}^{\mathrm{act}}.
  $$

**Remarks.** (1) Both $M_j$ and $N_j$ are sub-chain complexes of the chain-level blowup at the respective scales; all arrows are inclusions of chain complexes. (2) Intersection bridges minimize instantaneous changes ("shrink then grow"), while union bridges implement a "grow then shrink" handoff; either preserves zigzag well-posedness. (3) **Implementation naming:** we refer to the enter-layer normalization steps as **EnterByIntersection/EnterByUnion**, and to the intra-layer ordering routine as **LayerOrderLH** (sorting by $|J|, \dim \sigma$).

---

## Definition 6 (The staircase–zigzag filtration)

The **staircase–zigzag filtration** associated to $(X,\mathcal U,\{\alpha_j\})$ and a layer schedule $\{s_j\}$ is the finite zigzag diagram $\mathcal S$ obtained by concatenating

$$
\mathcal Z_0^{s_0}\ \dashleftarrow\ \text{(bridge)}\ \dashrightarrow\ \mathcal Z_1^{s_1}\ \dashleftarrow\ \text{(bridge)}\ \dashrightarrow\ \cdots\ \dashleftarrow\ \text{(bridge)}\ \dashrightarrow\ \mathcal Z_L^{s_L},
$$

where each “bridge” between $\mathcal Z_j^{s_j}$ and $\mathcal Z_{j+1}^{s_{j+1}}$ is chosen to be either the intersection bridge $M_j$ or the union bridge $N_j$ from Definition 5. Every arrow in $\mathcal S$ is an inclusion of **chain complexes**.

**Remarks.** (1) $\mathcal S$ is a legitimate input to any zigzag persistence algorithm (e.g., via a time-stamped add/remove-simplex encoding). (2) The special case where $\mathsf{Act}_j$ contains all nonempty $J$ (i.e., fully activated layers) reproduces the standard blowup filtration while retaining the $\Delta$-coordinate for localization. (3) **Implementation note:** when concatenating with adjacent segments, identical consecutive nodes may be coalesced in implementation; entering a layer from $A\cap C_j$ (for glue) or from $C_j$ (for peel) yields a zigzag isomorphic to the canonical $\mathcal Z_j^{s_j}$

---

## Definition 7 (Location map and cross-layer alignment)

Fix, once and for all, a **deterministic representative selection rule** for cycles (e.g., canonical representatives produced by a chosen zigzag algorithm). Let $\tilde z=\sum_s w_s\,(\sigma_s,I_s)$ be a $k$-cycle representative in $C_k(B_j^{\mathrm{act}})$ for some layer $j$. Define the **cover-mass** of index $i\in[m]$ and the associated **location vector**

$$
\mu_i(\tilde z) := \sum_s |w_s|\,\mathbf 1_{\,i\in I_s}\,\frac{1}{|I_s|},
\qquad
\Lambda_i(\tilde z) := \frac{\mu_i(\tilde z)}{\sum_{r=1}^m \mu_r(\tilde z)},
\qquad
\mathrm{Loc}_{\alpha_j}([\tilde z]) := (\Lambda_1,\dots,\Lambda_m)\in\Delta^{m-1}.
$$

**Remarks.** (1) Averaging by $|I_s|$ splits the weight of a blowup cell $(\sigma_s,I_s)$ evenly among its active cover indices, yielding a point of the barycentric simplex $\Delta^{m-1}$. (2) The value depends on the chosen representative; with a fixed selection rule it gives a reproducible **location profile** per bar across layers. (3) Under a fixed cover $\mathcal U$ no additional alignment is needed across $j$; if covers change in other applications, one may embed into a common simplex by zero-padding or by summing coordinates for merged cover sets.

---

## Additional background (self-contained notes)

- **Functoriality/monotonicity.** For $\alpha\le\beta$ we have $K_\alpha^J\subseteq K_\beta^J$ for all $J$, hence (at the chain level) $C_*(B_\alpha)\subseteq C_*(B_\beta)$ and $B_j^{\mathrm{act}}\subseteq B_{j'}^{\mathrm{act}}$ whenever $\alpha_j\le\alpha_{j'}$ and $\mathsf{Act}_j\subseteq\mathsf{Act}_{j'}$.
- **Why activation?** If $K_\alpha^J$ is discrete (only vertices), localized-homology–style steps create long but topologically inert early segments. Activating only after the first nondegenerate simplex appears postpones these inert segments without sacrificing later correctness; reduced $\tilde H_0$ may be used to down-weight residual degree-0 noise.
- **Compatibility with standard PH/LH.** On fully activated layers, $\pi_X: B_\alpha\to K_\alpha$ is (under standard hypotheses) a homotopy equivalence, and the chain-level model $C_*(B_\alpha)$ is chain-equivalent to any simplicial prism triangulation of $B_\alpha$; hence computing homology on $B_\alpha$ yields the same groups as on $K_\alpha$, now endowed with the interpretable location vector $\mathrm{Loc}$.



---

## Algorithm 1 — Staircase–Zigzag via Chain‑Level Blowup + ZigzagPersistence (LH‑style)

**Input.** Finite metric space $X$ with distance $d$; fixed cover $\mathcal U$ = { $X^i$ }; scale grid $\alpha_0<\cdots<\alpha_L$; max degree $k_{\max}$; coefficient field (e.g., $\mathbb Z_2$); layer schedule $s_j\in\{\mathrm{glue},\mathrm{peel}\}$; per‑layer bridge choice in $\{\mathrm{intersection},\mathrm{union}\}$.

**Output.** Zigzag barcodes $D_k$ for $0\le k\le k_{\max}$. Optionally: location trajectories $\mathrm{Loc}_\alpha$ for selected bars.

**Precompute.** For each nonempty $J$, activation threshold $a_J$ (e.g., the smallest scale where $K_\alpha^J$ contains a nondegenerate simplex of dimension $\le k_{\max}$).

### Main procedure

```
Initialize ZZ ← ZigzagPersistence()
Initialize idx : (sigma, J) ↦ integer         # cell index map
Initialize Bars[k] ← ∅ for k = 0..k_max
Initialize active set A ← ∅
Initialize time tag t ← 0                     # any totally ordered set

for j = 0..L do:
    # 1) Activated family and LH intra‑layer order
    Act_j ← { J ≠ ∅ : alpha_j ≥ a_J }
    C_j   ← LayerOrderLH(alpha_j, Act_j, k_max)   # list of cells (sigma, J) sorted by (|J|, dim sigma)

    # 2) Enter layer j in a state consistent with schedule
    if s_j == glue:
        EnterByIntersection(A, C_j)           # remove A \ C_j in reverse LH order; now A ← A ∩ C_j
    else:  # peel
        EnterByUnion(A, C_j)                  # add C_j \ A in LH order; now A ← C_j

    # 3) Realize the intra‑layer zigzag via add/remove
    if s_j == glue:
        for each block Delta ⊂ C_j in increasing LH order do:
            AddBlock(Delta, t); t ← NextTag(t); A ← A ∪ Delta
    else:  # peel
        for each block Delta ⊂ C_j in decreasing LH order do:
            RemoveBlock(Delta, t); t ← NextTag(t); A ← A \ Delta

    # 4) Bridge to the next layer if j < L
    if j < L:
        if Bridge_j == intersection:
            M_j ← A ∩ C_{j+1}
            for each block Delta ⊂ (A minus M_j) in decreasing LH order do:
                RemoveBlock(Delta, t); t ← NextTag(t); A ← A \ Delta
            for each block Delta ⊂ (C_{j+1} minus M_j) in increasing LH order do:
                AddBlock(Delta, t);    t ← NextTag(t); A ← A ∪ Delta
        else:  # union bridge
            for each block Delta ⊂ (C_{j+1} minus A) in increasing LH order do:
                AddBlock(Delta, t);    t ← NextTag(t); A ← A ∪ Delta
            for each block Delta ⊂ (A minus C_{j+1}) in decreasing LH order do:
                RemoveBlock(Delta, t); t ← NextTag(t); A ← A \ Delta

return Bars
```

For each cell $c=(\sigma, J)$ in $\Delta$ in any deterministic order:

1. bd $\leftarrow$ $\mathrm{LHBoundaryIndices}(\sigma, J)$      # boundary indices via the chain‑level product boundary
2. (i, birth) ← ZZ.add(bd, t)         # add cell with boundary indices at time t
3. idx[$(\sigma, J)$] $\leftarrow$ i
4. If birth ≠ None then let $k=\dim\sigma+|J|-1$ and append (birth, t) to Bars[k].

For each cell $c=(\sigma, J)$ in $\Delta$ in the reverse of the deterministic order used in AddBlock:

1. i $\leftarrow$ idx[$(\sigma, J)$]
2. birth ← ZZ.remove(i, t)
3. If birth ≠ None then let $k=\dim\sigma+|J|-1$ and append (birth, t) to Bars[k].

### Subroutine: LHBoundaryIndices(sigma, J)  # chain‑level blowup boundary

Let $p=\dim\sigma$ and list $J=\{j_0<\cdots<j_q\}$

### Subroutine: LayerOrderLH(alpha\_j, Act\_j, k\_max)

1. Build C\_j = { (sigma, J) : J ∈ Act\_j, sigma ∈ K\_alpha\_j^J, dim(sigma) + |J| − 1 ≤ k\_max }.
2. Sort C\_j by the key ( |J|, dim(sigma) ); break ties deterministically (e.g., lexicographic on vertex ids and the ordered tuple of indices in J).
3. Optionally partition C\_j into blocks of equal key (so updates are by blocks).

• EnterByIntersection($A$, $C$): remove $A\setminus C$ in decreasing LH order (result: $A\leftarrow A\cap C$). • EnterByUnion($A$, $C$): add $C\setminus A$ in increasing LH order (result: $A\leftarrow C$).

### Optional post‑processing: Location vectors

Given a representative cycle $z=\sum_s w_s\cdot(\sigma_s, J_s)$ at time $t$, define $\mu_i=\sum_s |w_s|\, \mathbf 1_{\{i\in J_s\}}/|J_s|$, then $\Lambda_i=\mu_i\big/\sum_r \mu_r$, and $\mathrm{Loc}(t)=(\Lambda_1,\ldots,\Lambda_m)$. This yields a per‑bar trajectory $\alpha\mapsto \mathrm{Loc}(\alpha)$ after aligning time tags with the scale grid.

### Notes (correctness and complexity)

• Correctness: the chain‑level blowup boundary (LH‑style) is chain‑equivalent to the geometric blowup and preserves homology within each layer; all add/remove steps realize inclusions, hence the full sequence is a valid zigzag. • Complexity: number of cells is $ \sum_{J \in \mathrm{Act}_j} |K_{\alpha_j}^J| $ across layers (no combinatorial binomial blow‑up from prism triangulation). Truncation to $k_{\max}$ further reduces size. • Coefficients: over $ \mathbb Z_2 $ the boundary ignores signs; for a prime $p$, incorporate the usual $(-1)$-signs in $ \mathrm{LHBoundaryIndices} $.

