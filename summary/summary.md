# Compositional Safety Verification with Max-SMT

Max-SAT
: $H_1 \wedge \dots H_n \wedge [S_1, \omega_1] \wedge \dots \wedge [S_m, \omega_m]$

Variables
: $\mathcal{V} = \lbrace v_1, \dots, v_n \rbrace$

Conjunctions of Linear Inequalities
: $\mathcal{F}(\mathcal{V}) = \lbrace // TODO \rbrace$

Locations
: $\mathcal{L} = \lbrace l_0, \dots, l_n \rbrace$

Transitions
: $\mathcal{T} = \lbrace (\ell, \tau, \ell') \mid \ell, \ell' \in \mathcal{L}, \tau \in \mathcal{F}(\mathcal{V} \cup \mathcal{V}') \rbrace$

Program
: $\mathcal{P} = (\mathcal{L}, \mathcal{T})$

State
: $s = (\ell, \upsilon)$ with $\ell \in \mathcal{L}$ and $\upsilon : \mathcal{V} \Rightarrow \mathbb{Z}$

Evaluation
: $(\ell, \upsilon) \rightarrow_t (\ell', \upsilon')$ with $t = (\ell, \tau, \ell')$ and both $\upsilon \models \tau$ and $\upsilon' \models \tau$

Assertion
: $(t, \phi)$

Safe for assertion
: $\forall (\ell_0, \upsilon_0): (\ell_0, \upsilon_0) \rightarrow_P^* \circ \rightarrow_t (\ell, \upsilon) \Rightarrow \upsilon \models \phi$

Program Invariant
: $\mathcal{I} : \mathcal{L} \rightarrow \mathcal{F}(\mathcal{V})$

Inductive Invariant
: Invariant with $\top \models \mathcal{I}(\ell_0)$ and $\forall (\ell, \tau, \ell') \in \mathcal{P}: \mathcal{I}(\ell) \wedge \tau \models \mathcal{I}(\ell')'$

Conditional Inductive Invariant
: Inductive Invariant $\mathcal{Q}$ with $\forall (\ell, \upsilon) \rightarrow_\mathcal{P} (\ell', \upsilon'): \upsilon \models \mathcal{Q}(\ell) \Rightarrow \upsilon' \models \mathcal{Q}(\ell')$

Farkas Lemma
: ?

Conditional Safety
: From a point in a program where a precondition holds every path to an assertion leads also to the fulfilment of the assertion

## Program Component

A program component $\mathcal{C} \subseteq \mathcal{T}$ is an SCC of a program

Entry Transitions
: $\mathcal{E}_\mathcal{C} = \lbrace (\ell, \tau, \ell') \in \mathcal{T} \mid t \notin \mathcal{C} \wedge \ell' \text{ appears in } \mathcal{C} \rbrace$
