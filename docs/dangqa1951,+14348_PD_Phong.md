_Journal of Computer Science and Cybernetics, V.35, N.4 (2019), 319–336_ DOI 10.15625/1813-9663/35/4/14348 

# **A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD WITH MULTI-GRANULARITY FUZZY PARTITIONING** 

PHAM DINH PHONG<sup>1</sup><sup>_,∗_</sup> , NGUYEN DUC DU<sup>1</sup> , NGUYEN THANH THUY<sup>2</sup> , 

HOANG VAN THONG<sup>1</sup> 

> 1 _Faculty of Information Technology, University of Transport and Communications, Hanoi, Vietnam_ 

> 2 _Faculty of Information Technology, University of Engineering and Technology, VNU, Hanoi, Vietnam_ 

_∗dinhphongpham@gmail.com_ 



**Abstract.** During last years, lots of the fuzzy rule based classifier (FRBC) design methods have been proposed to improve the classification accuracy and the interpretability of the proposed classification models. In view of that trend, genetic design methods of linguistic terms along with their (triangular and trapezoidal) fuzzy sets based semantics for FRBCs, using hedge algebras as the mathematical formalism, have been proposed. Those hedge algebras based design methods utilize semantically quantifying mapping values of linguistic terms to generate their fuzzy sets based semantics so as to make use of the existing fuzzy sets based classification reasoning methods for data classification. If there exists a classification reasoning method which bases merely on the semantic parameters of hedge algebras, fuzzy sets based semantics of the linguistic terms in the fuzzy classification rule bases can be replaced by hedge algebras-based semantics. This paper presents a FRBC design method based on hedge algebras approach by introducing a hedge algebra based classification reasoning method with multi-granularity fuzzy partitioning for data classification so that the semantics of linguistic terms in the rule bases can be hedge algebras-based semantics. Experimental results over 17 real world datasets are compared to the existing methods based on hedge algebras and the state-of-the-art fuzzy set theory-based approaches, showing that the proposed FRBC in this paper is an effective classifier and produces good results. 

**Keywords.** Classification Reasoning; Fuzzy Rule Based Classifier; Fuzziness Interval; Hedge Algebras; Multi-Granularity; Semantically Quantifying Mapping Values. 

## **1. INTRODUCTION** 

Fuzzy rule based systems (FRBSs) have been studied and applied efficiently in many different fields such as fuzzy control, data mining, etc. Unlike classical classifiers based on the statistical and probabilistic approaches [3, 8, 27, 32] which are the “black boxes” lacking of interpretability, the advantage of the FRBC model is that end-users can use the high interpretability fuzzy rule-based knowledge extracted automatically from data as their knowledge. 

In the FRBC design based on the fuzzy set theory approaches [1, 2, 6, 7, 21, 22, 23, 24, 35, 36, 38, 39, 41], the fuzzy partitions from which fuzzy rules are extracted are commonly pre-designed using fuzzy sets and then linguistic terms are intuitively assigned to 

_⃝_ c 2019 Vietnam Academy of Science & Technology 

320 

PHAM DINH PHONG et al. 

fuzzy sets. Furthermore, fuzzy partitions can be generated automatically from data by using discretization or granular computing mechanisms [37]. No matter how they are designed, the problem of the linguistic term design is not clearly studied although fuzzy rule bases are represented by linguistic terms with their fuzzy set based semantics. Many techniques have been proposed to achieve compact fuzzy rule systems with accuracy and interpretability trade-off extracted from data, such as using artificial neural network [33] or genetic algorithm [1, 2, 7, 21, 36, 38, 39, 41] by adjusting fuzzy set parameters to achieve the optimal fuzzy partitions and to select the optimal fuzzy rule based systems. However, the fuzzy set based semantics of linguistic terms are not preserved, leading to the affectedness of the interpretability of the fuzzy rule bases of classifiers. 

Hedge algebras (HAs) [9, 11, 12, 14, 17, 18] provide a mathematical formalism for designing the order based semantic structure of term domains of linguistic variables that can be applied to various application domains in the real life, such as fuzzy control [10, 26, 28, 29], expert systems [12], data mining [5, 13, 15, 16, 25, 40], fuzzy database [19, 42], image processing [20], timetabling [31], etc. The crucial idea of the hedge algebra based approach is that it reflects the nature of fuzzy information by the fuzziness of information. In [13, 15], HAs are utilized to model and design the linguistic terms for FRBCs. They exploit the inherent semantic order of linguistic terms that allows generating semantic constraints between linguistic terms and their integrated fuzzy sets. More specifically, when given values of fuzziness parameters, the semantically quantifying mapping (SQM) values of linguistic terms are computed and then associated fuzzy sets of linguistic terms are automatically generated from their own semantics. So, linguistic terms along with their fuzzy sets based semantics are generated by a procedure. Based on this formalism, an efficient fuzzy rule based classifier design method is developed. 

As set forth above, HAs can be utilized to design eminent FRBCs. However, we may wonder that why the semantics of linguistic terms in the fuzzy classification rule bases of FRBCs designed by the HAs based methodology are still fuzzy sets based semantics. The answer is that although linguistic terms are designed by HAs, the fuzzy set based classification reasoning methods proposed in the prior researches [21, 23, 24] are made use for data classification. If there is a classification reasoning method for data classification which bases merely on semantic parameters of hedge algebras, fuzzy sets based semantics of linguistic terms in the fuzzy classification rule bases can be replaced with hedge algebras based semantics. In response to that question, a classification reasoning method merely based on HAs for FRBC is presented in this paper. The idea is based on the Takagi-SugenoHedge algebras fuzzy model proposed in [26] to improve the forecast control based on models in such a way that membership functions of individual linguistic terms in Takagi-Sugeno fuzzy model are replaced with the closeness of semantically quantifying mapping values of adjacent linguistic values. That result is enhanced to build a classification reasoning method based on HAs which enables fuzzy sets based semantics of the linguistic terms in the fuzzy rule bases to be replaced with hedge algebras based semantics. Furthermore, the design of information granules plays an important role in designing FLRBCs, i.e., it is the basis for generating interpretable FLRBCs and impacts on the classification performance. Because of the semantic inheritance, with linguistic terms that are induced from the same primary term, the shorter the term, the more generality it has and vice versa. Therefore, with the single-granularity structure, all linguistic terms just appear in a fuzzy partition leading 

321 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 

to the semantics of shorter terms are reduced and become more specific. Contrarily, the multi-granularity structure retains the generality of shorter linguistic terms in the rule bases because linguistic terms which have the same length form a fuzzy partition. That is why a hedge algebra based classification reasoning method with multi-granularity fuzzy partitioning for data classification is introduced in this paper. Experimental results over 17 real world datasets show the efficiency of the multi-granularity structure design in comparison with the single one as well as show the efficiency of the proposed classifier in comparison with the state-of-the-art methods based on hedge algebras and fuzzy set theory. 

The rest of the paper is organized as follows: Section 2 presents fuzzy rule based classifier design based on hedge algebras and the proposed hedge algebras based classification reasoning method for the FRBCs. Section 3 presents experimental evaluation studies and discussions. Conclusions and remarks are included in Section 4. 

## **2. FUZZY RULE BASED CLASSIFIER DESIGN BASED ON HEDGE ALGEBRAS** 

## **2.1. Hedge algebras for the semantic representation of linguistic terms** 

To formalize the nature structure of the linguistic variables, a mathematic structure, so-called the hedge algebra, has been introduced and examined by N. C. Ho et al. [17, 18]. Assume that _X_ is a linguistic variable and the linguistic value domain of _X_ is _Dom_ ( _X_ ). A hedge algebra _AX_ of _X_ is a structure _AX_ = ( _X_ , _G_ , _C_ , _H_ , _≤_ ), where _X_ is a set of linguistic terms of _X_ and _X ⊆ Dom_ ( _X_ ); _G_ is a set of two generator terms _c_<sup>_−_</sup> and _c_<sup>+</sup> , where _c_<sup>_−_</sup> is the negative primary term, _c_<sup>+</sup> is the positive primary term and _c_<sup>_−_</sup> _≤ c_<sup>+</sup> ; _C_ is a set of term constants, _C_ = _{_ **_0_** , _W_ , **_1_** _}_ , satisfying the relation order **_0_** _≤ c_<sup>_−_</sup> _≤ W ≤ c_<sup>+</sup> _≤_ **_1_** ; **_0_** and **_1_** are the least and the greatest terms, respectively; _W_ is the neutral term; _H_ is a set of hedges of _X,_ where _H_ = _H_<sup>_−_</sup> _∪ H_<sup>+</sup> , _H_<sup>_−_</sup> and _H_<sup>+</sup> are the set of negative and positive hedges, respectively; _≤_ is an order relation induced by the inherent semantics of terms of _X_ . 

When a hedge acts on a non-constant term, a new linguistic term is induced. Each linguistic term _x_ in _X_ is represented as the string representation, i.e., either _x_ = _c_ or _x_ = _hm_ . . . _h_ 1 _c_ , where _c ∈{c_<sup>_−_</sup> , _c_<sup>+</sup> _} ∪ C_ and _hj ∈ H_ , _j_ = 1, . . . , _m_ . All linguistic terms generated from _x_ by using the hedges in _H_ can be abbreviated as _H_ ( _x_ ). If all linguistic terms in _X_ and all hedges in _H_ have a linear order relation, respectively, _AX_ is the linear hedge algebras. _AX_ is built from some characteristics of the inherent semantics of linguistic terms which are expressed by the semantic order relationship “ _≤_ ” of _X_ . 

Two primary terms _c_<sup>_−_</sup> and _c_<sup>+</sup> possess their own converse semantic tendencies. For convenience, _c_<sup>+</sup> possesses the positive tendency and it has positive sign written as sign( _c_<sup>+</sup> ) = +1. Similarly, _c_<sup>_−_</sup> possesses the negative tendency and it has negative sign written as sign( _c_<sup>_−_</sup> ) = _−_ 1 _._ As the semantic order relationship, we have _c_<sup>_−_</sup> _≤ c_<sup>+</sup> . For example, “ _old_ ” possesses the positive tendency, “ _young_ ” possesses the negative tendency and “ _young_ ” _≤_ “ _old_ ”. 

Each hedge possesses tendency to decrease or increase the semantics of two primary terms. For example, “ _very young_ ” _≤_ “ _young_ ” and “ _old_ ” _≤_ “ _very old_ ”, the hedge _very_ makes the semantics of “ _young_ ” and “ _old_ ” increased. “ _young_ ” _≤_ “ _less young_ ” and “ _less old_ ” _≤_ “ _old_ ”, the hedge _less_ makes the semantics of “ _young_ ” and “ _old_ ” decreased. It is said that _very_ is the positive hedge and _less_ is the negative hedge. We denote the _H_<sup>_−_</sup> = _{h−q_ , 

322 

PHAM DINH PHONG et al. 

. . . , _h−_ 1 _}_ is a set of negative hedges where _h−q ≤_ . . . _≤ h−_ 2 _≤ h−_ 1, _H_<sup>+</sup> = _{h_ 1, . . . , _hp}_ is a set of positive hedges where _h_ 1 _≤ h_ 2 _≤_ . . . _≤ hp_ and _H_ = _H_<sup>_−_</sup> _∪ H_<sup>+</sup> . If _h ∈ H_<sup>_−_</sup> , sign( _h_ ) = _−_ 1 and if _h ∈ H_<sup>+</sup> , sign( _h_ ) = +1. If both hedges _h_ and _k_ in _H_<sup>_−_</sup> or _H_<sup>+</sup> , we say that _h_ and _k_ are compatible, whereas, _h_ and _k_ are inverse each other. 

Each hedge possesses tendency to decrease or increase the semantics of other hedge. If _k_ makes the semantic of _h_ increased, _k_ is positive with respect to _h_ , whereas, if _k_ makes the sematic of _h_ decreased, _k_ is negative with respect to _h_ . The negativity and positivity of hedges do not depend on the linguistic terms on which they act. For example, _V_ is positive with respect to _L_ , we have _x ≤ Lx_ then _Lx ≤ VLx_ , or _Lx ≤ x_ then _VLx ≤ Lx_ . One hedge may have a relative sign with respect to another. sign( _k_ , _h_ ) = +1 if _k_ strengthens the effect tendency of _h_ , whereas, sign( _k_ , _h_ ) = _−_ 1 if _k_ weakens the effect tendency of _h_ . Thus, the sign of term _x_ , _x_ = _hmhm−_ 1 _. . . h_ 2 _h_ 1 _c_ , is defined by 

sign( _x_ ) = sign( _hm_ , _hm−_ 1) _×_ . . . _×_ sign( _h_ 2, _h_ 1) _×_ sign( _h_ 1) _×_ sign( _c_ ). 

The meaning of the sign of term is that sign( _hx_ ) = +1 _→ x ≤ hx_ and sign( _hx_ ) = _−_ 1 _→ hx ≤ x_ . 

Semantic inheritance in generating linguistic terms by using hedges: When a new linguistic term _hx_ is generated from a linguistic term _x_ by using the hedge _h_ , the semantic of the new linguistic term is changed but it still conveys the original semantic of _x_ . This means that the semantic of _hx_ is inherited from _x_ . 

As set forth above, HAs are the qualitative models. Therefore, to apply HAs to solve the real world problems, some characteristics of HAs need to be characterized by quantitative concepts based on qualitative term semantics. 

On the semantic aspect, _H_ ( _x_ ), _x ∈ X_ , is the set of linguistic terms generated from _x_ and their semantics are changed by using the hedges in _H_ but still convey the original semantic of _x_ . So, _H_ ( _x_ ) reflects the fuzziness of _x_ and the length of _H_ ( _x_ ) can be used to express the _fuzziness measure_ of _x_ , denoted by _fm_ ( _x_ ). When _H_ ( _x_ ) is mapped to an interval in [0, 1] following the order structure of _X_ by a mapping _v_ , it is called the _fuzziness interval_ of _x_ and denoted by _ℑ_ ( _x_ ). 

A function _fm_ : _X →_ [0, 1] is said to be a _fuzziness measure_ of _AX_ provided that it satisfies the following properties: 

(FM1) _fm_ ( _c_<sup>_−_</sup> ) + _fm_ ( _c_<sup>+</sup> ) = 1 and<sup>�</sup> _fm_ ( _hu_ ) = _fm_ ( _u_ ) for _∀u ∈ X_ ; _h∈H_ 

(FM2) _fm_ ( _x_ ) = 0 for all _H_ ( _x_ ) = _x_ , especially, _fm_ ( **_0_** ) = _fm_ ( _W_ ) = _fm_ ( **_1_** ) = 0; 

(FM3) _∀x, y ∈ X, ∀h ∈ H_ , the proportion<sup>_<u>f</u>_</sup> _fm_<sup>_m_</sup><sup><u>(</u></sup> (<sup>_hx_</sup> _x_ )<sup><u>)</u>=</sup><sup>_<u>f</u>_</sup> _fm_<sup>_m_</sup><sup><u>(</u></sup> (<sup>_h_</sup> _y_<sup>_<u>y</u>_</sup> )<sup><u>)</u>which does not depend</sup> 

on any particular linguistic term on _X_ is called the fuzziness measure of the hedge _h_ , denoted by _µ_ ( _h_ ). 

From (FM1) and (FM3), the fuzziness measure of linguistic term _x_ = _hm_ . . . _h_ 1 _c_ can be computed recursively that _fm_ ( _x_ ) = _µ_ ( _hm_ ). . . _µ_ ( _h_ 1) _fm_ ( _c_ ), where<sup>�</sup> _µ_ ( _h_ ) = 1 and _c ∈ h∈H {c_<sup>_−_</sup> , _c_<sup>+</sup> _}_ . 

Semantically quantifying mappings (SQMs): The semantically quantifying mapping of _AX_ is a mapping _v_ : _X →_ [0 _,_ 1] which satisfies the following conditions: 

323 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 

(SQM1) It preserves the order based structure of _X_ , i.e., _x ≤ y → v_ ( _x_ ) _≤ v_ ( _y_ ) _, ∀x ∈ X_ ; (SQM2) It is one-to-one mapping and _v_ ( _x_ ) is dense in [0, 1]. Let _fm_ be a fuzziness measure on _X_ . _v_ ( _x_ ) is computed recursively based on _fm_ as follows: 

1. _v_ ( _W_ ) = _θ_ = _fm_ ( _c_<sup>_−_</sup> ) _, v_ ( _c_<sup>_−_</sup> ) = _θ − αfm_ ( _c_<sup>_−_</sup> ) = _βfm_ ( _c_<sup>_−_</sup> ) _, v_ ( _c_<sup>+</sup> ) = _θ_ + _αfm_ ( _c_<sup>+</sup> ); 



where _j ∈_ [- _q, p_ ] = _{j_ : - _q ≤ j ≤ p, j̸_ = 0 _}_ and 



## **2.2. Fuzzy rule based classifier design based on hedge algebras** 

A fuzzy rule based classifier design problem _P_ is defined as: A set **_P_** = _{_ ( **_d_** _p_ , _Cp_ ) _|_ **_d_** _p ∈_ **_D_** , _Cp ∈_ **_C_** , _p_ = 1, . . . , _m}_ of _m_ patterns, where **_d_** _p_ = [ _dp,_ 1 _, dp,_ 2 _, ..., dp,n_ ] is the row _p_<sup>_th_</sup> , **_C_** = _{Cs|s_ = 1, . . . , _M }_ is the set of _M_ class labels, _n_ is the number of features of the dataset **_P_** . 

The fuzzy rule based system of the FRBCs used in this paper is the set of weighted fuzzy rules in the following form [21, 23, 24] 

Rule _Rq_ : IF _X_ 1 is _Aq,_ 1 AND ... AND _Xn_ is _Aq,n_ THEN _Cq_ with _CF q,_ for _q=1,. . . ,N,_ 



where _X_ = _{Xj, j_ = 1 _, ..., n}_ is the set of _n_ linguistic variables corresponding to _n_ features of the dataset **_P_** , _Aq,j_ is the linguistic terms of the _j_<sup>_th_</sup> feature _Fj_ , _Cq_ is a class label and _CF q_ is the rule weight of _Rq_ . The rule _Rq_ is abbreviated as the following short form 



where **_A_** _q_ is the antecedent part of the _q_<sup>_th_</sup> -rule. 

Solving the problem _P_ is to extract from **_P_** a set **_S_** of fuzzy rules in the form (1) in order to achieve a compact FRBC based on **_S_** comes with high classification accuracy and suitable interpretability. The general method of FRBC design with the semantics of linguistic terms based on the hedge algebras comprises two following phases [15, 16]: 

1. Genetically design linguistic terms along with their fuzzy-set-based semantics for each feature of the designated dataset in such a way that only semantic parameter values are adjusted, as a result, near optimal semantic parameter values are achieved by the interaction between semantics of linguistic terms and the data. 

2. An evolutionary algorithm is applied to select near optimal fuzzy classification rule based systems having a quite suitable interpretability–accuracy trade-offs from data by using a given near optimal semantic parameter values provided by the first phase for fuzzy rule based classifiers. 

324 

PHAM DINH PHONG et al. 

HAs provides a formalism basis for generating quantitative semantics of linguistic terms from their qualitative semantics. This formalism is applied to genetically design linguistic terms along with the integrated fuzzy set based semantics for fuzzy rule based classifiers. Hereafter are the summaries of two above steps: 

Each feature _j_<sup>_th_</sup> of the designated dataset is associated with an hedge algebra _AX j_ , induces all linguistic terms _Xj,_ ( _kj_ ) with the maximum length _kj_ having the order based inherent semantics of linguistic terms. Given a value of the semantic parameters Π, which includes fuzziness measures _fm_ ( _c_<sup>_−_</sup> _j_<sup>)and</sup><sup>_µ_(</sup><sup>_hj,i_)ofthenegativeprimaryterm</sup><sup>_c_</sup> _j_<sup>_−_and</sup><sup>_hj,i_,</sup> respectively, and a positive integer _kj_ for limiting the designed term lengths, quantifying mapping values _v_ ( _xj,i_ ) _, xj,i ∈ Xj,k_ for all _k ≤ kj_ and the _kj_ -similarity intervals S _kj_ ( _Xj,i_ ) of linguistic terms in _Xj,kj_ +2 are computed and they constitute a unique fuzzy partition of the _j_<sup>_th_</sup> attribute. After fuzzy partitions of all attributes are constructed, fuzzy rule conditions will be specified based on these partitions. 

Among the _kj_ -similarity intervals of a given fuzzy partition, there is a unique interval S _kj_ � _xj,i_ ( _i_ )� containing _j_<sup>_th_</sup> -component _dp,j_ of _dp_ pattern. All _kj_ -similarity intervals which contain _dp,j_ component define a hyper-cube _Hp_ , and fuzzy rules are only induced from this type of hyper-cube. A fuzzy rule generated from _Hp_ for the class _Cp_ of _dp_ is so-called a _basic fuzzy rule_ and it has the following form 



Only one basic fuzzy rule which has the length _n_ can be generated from the data pattern _dp_ . To generate the fuzzy rule with the length _L ≤ n_ , so-called the _secondary rules_ , some techniques should be used for generating fuzzy combinations, for example, generate all _k_ - combinations (1 _≤ k ≤ L_ ) from the given set of _n_ features of dataset _P_ . 



where 1 _≤ j_ 1 _≤_ . . . _≤ jt ≤ n_ . The consequence class _Cq_ of the rule _Rq_ is determined by the confidence measure _c_ ( **_A_** _q ⇒ Ch_ ) [20, 21] of _Rq_ 



The confidence of a fuzzy rule is computed as 



where _µ_ **_A_** _q_ ( _dp_ ) is the compatibility grade of the pattern _dp_ with the antecedent of the rule _Rq_ and commonly computed as 



As trying to generate all possible combinations, the maximum of number fuzzy combinations is � _L Cn_<sup>_i_,sothemaximumofthe</sup><sup>_secondaryrules_is</sup><sup>_m ×_</sup> � _L Cn_<sup>_i_.</sup> _i_ =1 _i_ =1 

325 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 

To eliminate less important rules, a screening criterion is used to select a subset **_S_** 0 with _NR_ 0 fuzzy rules from the candidate rule set, called an _initial fuzzy rule set_ . Candidate rules are divided into _M_ groups, sort rules in each group by a screening criterion. Select from each group _NB_ 0 rules, so the number of initial fuzzy rules is _NR_ 0 = _NB_ 0 _× M_ . The screening criterion can be the confidence _c_ , the support _s_ or _c × s_ . The confidence is computed by the formula (4), the support is computed as following formula [20] 



To improve the accuracy of classifiers, each fuzzy rule is assigned a rule weight and it is commonly computed by the following formula [20] 



where _cq,_ 2 _nd_ is computed as 



The classification reasoning method commonly used to classify the data pattern _dp_ is Single Winner Rule (SWR). The winner rule _Rw ∈_ **_S_** (a classification rule set) is the rule which has the maximum of the product of the compatibility grade _µ_ **_A_** _q_ ( _dp_ ) and the rule weight _CF_ ( **_A_** _q ⇒ Cq_ ), and the classified class _Cw_ is the consequence part of this rule. 



This fuzzy rule generation process is called the initial fuzzy rule set generation procedure **IFRG** (Π, **_P_** , _NR_ 0 _, L_ ) [15], where Π is a set of semantic parameter values and _L_ is the maximum of rule length. 

Each specific dataset needs a different set of semantic parameter values to adapt to the data distribution of it, i.e., the quality of the classifier is improved. Thus, an evolutionary algorithm is needed to find optimal semantic parameter values for a specific dataset. When having optimal semantic parameter values, they are used to extract an _initial fuzzy rule set_ and an evolutionary algorithm used to find a subset of the fuzzy classification rules **_S_** from **_S_** 0 having a suitable interpretability–accuracy trade-offs for FRBCs. 

## **2.3. Hedge algebras based reasoning method for fuzzy rule based classifier** 

Up to now, fuzzy rule based classifier design methods, using the hedge algebra methodology [13, 15] induce fuzzy sets based semantics of linguistic terms for FRBCs because the authors would like to make use of the fuzzy set based classification reasoning method proposed in the fuzzy set based approaches [21, 23, 24]. This research aims at proposing hedge algebras based classification reasoning method with multi-granularity fuzzy partitioning for FRBCs and shows the efficiency of the proposed ones by the experiments on a considerable real world datasets. 

In [26], the authors propose a Takagi-Sugeno-Hedge algebra fuzzy model to improve the forecast control based on the models by using the closeness of semantically quantifying mapping values of adjacent linguistic terms instead of the grade of the membership function of each individual linguistic term. That idea is summarized as follows: 

326 

PHAM DINH PHONG et al. 

- _v_ ( _xi_ ), _v_ ( _x_ 0) and _v_ ( _xk_ ) are the SQM values of the linguistic terms _xi_ , _x_ 0 and _xk_ with the semantic order _xi ≤ x_ 0 _≤ xk_ , respectively. 

- _ηi_ which is the closeness of _v_ ( _xi_ ) to _v_ ( _x_ 0) is defined as _ηi_ =<sup><u>(</u></sup><sup>_v_</sup><sup><u>(</u></sup><sup>_xk_</sup><sup><u>)</u></sup><sup>_−v_</sup><sup><u>(</u></sup><sup>_x_0))</sup> ( _v_ ( _xk_ ) _− v_ ( _xi_ ))<sup>and</sup><sup>_ηk_</sup> 

- which is the closeness of _v_ ( _x_ 2) to _v_ ( _x_ 0) is defined as _ηk_ =<sup><u>(</u></sup><sup>_v_</sup><sup><u>(</u></sup><sup>_x_0)</sup><sup>_−v_</sup><sup><u>(</u></sup><sup>_xi_</sup><sup><u>))</u></sup> ( _v_ ( _xk_ ) _− v_ ( _xi_ ))<sup>,where</sup><sup>_ηi_+</sup> 

- _ηk_ = 1 and 0 _≤ ηi_ , _ηk ≤_ 1. 

That idea is advanced to apply to make the hedge algebra based classification reasoning methods for FRBCs in two cases as follows. 

## **_In case of single granularity structure_** 

In the single granularity structure design, all linguistic terms _X_ ( _kj_ ) with different term length _k_ (1 _≤ k ≤ kj_ ) appear at the same level _kj_ . Therefore, at the level _kj_ of the _j_<sup>_th_</sup> -feature of the designated dataset, there are the SQM values of all linguistic terms _X_ ( _kj_ ) with the semantic order _v_ ( _xj,i−_ 1) _≤ v_ ( _xj,i_ ) _≤ v_ ( _xj,i_ +1), _xj,i ∈ X_ ( _kj_ ). For a data point _dp,j_ of the data pattern _dp_ (has been normalized to [0, 1]), the closeness of _dp,j_ to _v_ ( _xj,i_ ) is defined as: 







_Figure 1_ . The position of data point d _p,j_ at the level _kj_ = 2 in the single granularity structure 

Figure 1 shows the position of data point _dp,j_ between the SQM values of the linguistic terms in case _kj_ is 2. In this example, _dp,j_ is between _v_ ( _Vc_<sup>_−_</sup> ) and _v_ ( _c_<sup>_−_</sup> ), so the closeness of . _dp,j_ to _v_ ( _c_<sup>_−_</sup> ) is _ηdp,j_ =<sup>_v_</sup><sup><u>(</u></sup><sup>_Lc−_</sup><sup><u>)</u></sup><sup>_−v_</sup><sup><u>(</u></sup><sup>_c−_</sup><sup><u>)</u></sup> 



## **_In case of multi-granularity structure_** 

In the multi-granularity structure design, linguistic terms with the same term length _Xk_ (including two constants 0 and 1) which have the partial order make a separate fuzzy partition. At the level _k_ (0 _≤ k ≤ kj_ ), there are SQM values of linguistic terms _Xk_ with the partial semantic order, i.e., _v_ ( _x_<sup>_k_</sup> _j,i−_ 1<sup>)</sup><sup>_≤v_(</sup><sup>_xk_</sup> _j,i_<sup>)</sup><sup>_≤v_(</sup><sup>_xk_</sup> _j,i_ +1<sup>)</sup><sup>_,xk_</sup> _j,i_<sup>_∈Xk_.</sup> For a data point _dp,j_ of the data pattern _dp_ , the closeness of _dp,j_ to _v_ ( _x_<sup>_k_</sup> _j,i_<sup>)isdefinedas:</sup> 



327 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 



_Figure 2_ . The position of data point d _p,j_ at the level _k_ = 2 in the multi-granularity structure 

For example, Figure 2 shows the position of data point _dp,j_ between SQM values of linguistic terms in case _kj_ is 2. In this case, _dp,j_ is between _v_ ( _Vc_<sup>_−_</sup> ) and _v_ ( _Lc_<sup>_−_</sup> ), so the . closeness of _dp,j_ to _v_ ( _Lc_<sup>_−_</sup> ) is _ηdp,j_ =<sup>_v_</sup><sup><u>(</u></sup><sup>_Lc_+)</sup><sup>_−v_</sup><sup><u>(</u></sup><sup>_Lc−_</sup><sup><u>)</u></sup> _v_ ( _Lc_<sup>+</sup> ) _− dp,j_ 

We can see that the generality of shorter linguistic terms are preserved with the multigranularity structure design. The predictability can be improved by high generality classifiers, whereas, high specificity classifiers are good for the particular data. The problem of finding a suitable trade-off between the generality and the specificity of linguistic terms can be given out with the multi-granularity structure design method. 

After the formula of the closeness measure of a data point to a specified SQM value of a linguistic term is defined, it is used to compute the compatibility grade of a data pattern _dp_ with the antecedent of the rule _Rq_ as follows: 

- + The compatibility grade _µ_ **_A_** _q_ ( _dp_ ) in the formula (4), (6) and (9) is replaced with _ηAq_ ( _dp_ ). 

+ _η_ **_A_** _q_ ( _dp_ ) is computed as 



+ The formula (4) becomes 



+ The formula (6) becomes 



+ The formula (9) becomes 



Because the new compatibility grade _η_ **_A_** _q_ ( _dp_ ) is computed purely based on the SQM values of the linguistic terms, there is not any fuzzy sets in the proposed model. In the proposed hedge algebras based classification reasoning method, the membership function is replaced with the closeness measure of the data point to the SQM value of the linguistic term. 

328 

PHAM DINH PHONG et al. 

## **3. EXPERIMENTAL STUDY EVALUATIONS AND DISCUSSIONS** 

This section presents experimental results of the FRBC applying the proposed hedge algebras based classification reasoning with multi-granularity fuzzy partitioning in comparison with the state-of-the-art results of methods based on hedge algebras [13, 15] and fuzzy sets theory [2]. The real world datasets used in our experiments can be found on the KEELDataset repository: http://sci2s.ugr.es/keel/datasets.php and shown in the Table 1. Firstly, two granularity design methods, single granularity and multi-granularities, are compared with each other in order to show the better one. Secondly, the better one is compared to the existing hedge algebras based classifiers proposed in [13, 15] and the fuzzy set theory based approaches proposed in [2]. The comparison conclusions will be made based on the test results of the Wilcoxon’s signed rank tests [4]. To make a comparative study, the same cross validation method is used when comparing the methods. All experiments use the ten-folds cross-validation method in which the designated dataset is randomly divided into ten folds, nine folds for the training phase and one fold for the testing phase. Three experiments are executed for each dataset and results of the classification accuracy and the complexity of the FRBCs are averaged out, respectively. 

_Table 1_ . The datasets used to evaluate in this research 

|**No.**|**Dataset**<br>**Name**|**Number of**<br>**attributes**|**Number of**<br>**classes**|**Number of**<br>**patterns**|
|---|---|---|---|---|
|1|Australian|14|2|690|
|2|Bands|19|2|365|
|3|Bupa|6|2|345|
|4|Dermatology|34|6|358|
|5|Glass|9|6|214|
|6|Haberman|3|2|306|
|7|Heart|13|2|270|
|8|Ionosphere|34|2|351|
|9|Iris|4|3|150|
|10|Mammogr.|5|2|830|
|11|Pima|8|2|768|
|12|Saheart|9|2|462|
|13|Sonar|60|2|208|
|14|Vehicle|18|4|846|
|15|Wdbc|30|2|569|
|16|Wine|13|3|178|
|17|Wisconsin|9|2|683|



In order to have significant comparisons, reduce the searching space in the learning processes and there is no big imbalance between _fm_ ( _c_<sup>_−_</sup> _j_<sup>)and</sup><sup>_fm_(</sup><sup>_c_+</sup> _j_<sup>),andbetween</sup><sup>_µ_(</sup><sup>_Lj_)</sup> and _µ_ ( _Vj_ ), constraints on semantic parameter values should be the same as ones used in the compared methods (in [13]) and they are applied as follows: The number of both negative and positive hedges is 1, the negative hedge is “Less” ( _L_ ) and the positive hedge is “Very” 

329 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 

( _V_ ); 0 _≤ kj ≤_ 3; 0.2 _≤_ � _fm_ ( _c_<sup>_−_</sup> _j_<sup>)</sup><sup>_, fm_(</sup><sup>_c_+</sup> _j_<sup>)</sup> � _≤_ 0.8; _fm_ ( _c_<sup>_−_</sup> _j_<sup>) +</sup><sup>_fm_(</sup><sup>_c_</sup> _j_<sup>+)=1;0.2</sup><sup>_≤µ_(</sup><sup>_Lj_),</sup> _µ_ ( _Vj_ ) _≤_ 0.8; and _µ_ ( _Lj_ ) + _µ_ ( _Vj_ ) = 1. 

To optimize semantic parameter values and select the best fuzzy rule set for FRBCs, the multi-objective particle swarm optimization (MOPSO) [30, 34] is utilized. The algorithm parameter values of MOPSO used in the semantic parameter value optimization process are as follows: The number of generations is 250; The number of particles of each generation is 600; Inertia coefficient is 0.4; The self-cognitive factor is 0.2; The social cognitive factor is 0.2; The number of the initial fuzzy rules is equal to the number of attributes; The maximum of rule length is 1. Most of the algorithm parameter values of MOPSO used in the fuzzy rule selection process are the same, except, the number of generations is 1000; The number of initial fuzzy rules _|S_ 0 _|_ = 300 _×_ number of classes; The maximum of rule length is 3. 

## **3.1. Single granularity versus multi-granularities** 

In the fuzzy set theory based approaches, as there is no formal links between linguistic terms of variables and their intuitively designed fuzzy sets, one may be confused to assign linguistic terms to pre-designed fuzzy sets of the multi-granularity structures. Whereas, in the HAs-approach, linguistic terms which have the same length and partially ordered form a fuzzy partition. So, there is no interpretability loss when using multi-granularity structures. This sub-section represents the comparison results between the fuzzy rule based classifier applying the hedge algebras based classification reasoning with single granularity structure (namely HABR-SIG) and the one applying the hedge algebras based classification reasoning with multi-granularity structure (namely HABR-MUL) and shows the important role of the information granule design. 

Experimental results of HABR-MUL and HABR-SIG are shown in the Table 2, noting that the column #R _×_ #C shows the complexities of extracted fuzzy rule bases of the classifiers; _Pte_ is the classification accuracies of the test sets; _̸_ = _Pte_ and _̸_ = _R×C_ columns show the differences of the classification accuracies and the complexities of the compared classifiers, respectively. Better values are shown in bold face. 

As intuitively recognized from the Table 2, classification accuracies of testing sets of HABR-MUL are better than HABR-SIG on 13 of 17 datasets. The mean value of the classification accuracies on all experimented datasets of HABR-MUL is greater than HABRSIG while the mean value of the complexity measures of fuzzy rule based systems between them are not much different. Therefore, to know whether the differences of experimental results between two granularity structures are significant or not, Wilcoxon’s signed-rank test is applied to test the accuracies and the complexities of fuzzy rule based systems extracted from two granularity structures. It is assumed that their accuracies and complexities are statistically equivalent (null-hypothesis), respectively. 

Statistical testing results of the accuracies and the complexities obtained by Wilcoxon’s signed-rank tests at level _α_ = 0.05 are shown in the Table 3 and Table 4, respectively. The abbreviation terms used in the statistical test result tables from now on: VS column is the list of the compared method names; E. is Exact; A. is Asymptotic. 

As shown in the Table 4, since the _p-value >_ 0.05, the _null-hypothesis_ is not rejected. There is no significant difference of the complexities between the two compared methods. Therefore, there is no need to take the complexity of the FRBCs into account in this case 

330 

PHAM DINH PHONG et al. 

_Table 2_ . The experimental results of the HABR-MUL and the HABR-SIG classifiers 

|**Dataset**|**HABR-M**<br>|**UL**<br>|**HABR-SI**<br>|**G**<br>|_̸_=_R×C_|_̸_=_Pt_|
|---|---|---|---|---|---|---|
||#_R×#C_|_Tte_|#_R×#C_|_Tte_|_̸_|_̸e_|
|Australian|46.38|**87.29**|53.24|86.33|-6.86|0.96|
|Bands|53.22|73.53|60.60|**73.61**|-7.38|-0.08|
|Bupa|152.76|**72.13**|203.13|71.82|-50.37|0.31|
|Dermatology|215.64|**96.55**|191.84|95.47|23.80|1.08|
|Glass|403.08|73.09|318.68|**73.77**|84.40|-0.68|
|Haberman|9.00|77.11|8.82|77.11|0.18|0.00|
|Heart|105.16|**83.95**|122.92|83.70|-17.76|0.25|
|Ionosphere|58.29|**93.18**|92.80|92.22|-34.51|0.96|
|Iris|30.35|**98.67**|28.41|97.56|1.94|1.11|
|Mammogr.|50.57|**84.35**|85.04|84.33|-34.47|0.02|
|Pima|57.65|**77.28**|52.02|76.18|5.63|1.10|
|Saheart|59.40|72.23|56.40|**72.60**|3.00|-0.37|
|Sonar|64.62|**79.29**|61.80|77.52|2.82|1.77|
|Vehicle|236.17|**68.20**|333.94|68.01|-97.77|0.19|
|Wdbc|47.35|**96.31**|47.15|95.26|0.20|1.05|
|Wine|34.00|**99.61**|43.20|99.44|-9.20|0.17|
|Wisconsin|49.85|96.99|66.71|**97.19**|-16.86|-0.20|
|**Mean**|**98.44**|**84.10**|**107.45**|**83.65**|||



_Table 3_ . The comparison result of the accuracy of HABR-MUL and HABR-SIG classifiers using the Wilcoxon signed rank test at level _α_ = 0.05 

|**VS**|**R**<sup>+</sup>|**R**<sup>_−_</sup>|**E.** **_P_-value**|**A.** **_P_-value**|**Hypothesis**|
|---|---|---|---|---|---|
|HABR-MUL vs HABR-SIG|112.0|24.0|0.0214|0.020558|Rejected|



_Table 4_ . The comparison result of the complexity of HABR-MUL and HABR-SIG classifiers using the Wilcoxon signed rank test at level _α_ = 0.05 

|**VS**|**R**<sup>+</sup>|**R**<sup>_−_</sup>|**E.** **_P_-value**|**A.** **_P_-value**|**Hypothesis**|
|---|---|---|---|---|---|
|HABR-MUL vs HABR-SIG|104.0|49.0|_≥_0_._2|0.185016|Not rejected|



of comparison. The comparison result of the classification accuracies is shown in the Table 3. Since the _p-value_ = 0.0214 _<_ 0.05, the _null-hypothesis_ is rejected. Based on statistical testing results, we can state that the multi- granularity based classifier outperforms the single granularity based classifier. In the next sub-sections, the multi-granularity structure is the default granular design method in our experiments. 

331 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 

## **3.2. The proposed classifier versus the existing hedge algebras based classifiers** 

This sub-section presents the evaluation of the proposed classifier (HABR-MUL) in comparisons with the existing hedge algebras based classifiers. For the reading convenience, the hedge algebras based classifier with the triangular [13] and trapezoidal [15] fuzzy set based semantics of linguistic values are named as HATRI and HATRA, respectively. Their experimental results in the Table 5 show that HABR-MUL has better classification accuracies on 15 and 13 of 17 experimental datasets than HATRI and HATRA, respectively. The mean value of the classification accuracies of HABR-MUL is higher than HATRI and HATRA (84.10% in comparison with 82.82% and 83.58, respectively). The mean value of the fuzzy rule base complexities of HABR-MUL is a bit lower than both HATRI and HATRA (98.44 in comparison with 104.52 and 103.79, respectively). 

_Table 5_ . Experimental results of HABR-MUL, HATRI and HATRA classifiers 

|**Dataset**|**HABR-**<br>|**MUL**|**HATRI**<br>||_̸_=_R×C_|_̸_=_P _|**HATRA**<br>||_̸_=_R×C_|_̸_=_P _|
|---|---|---|---|---|---|---|---|---|---|---|
||#_R×#C_|_Tte_|#_R×#C_|_Tte_|_̸_|_̸ te_|#_R×#C_|_Tte_|_̸_|_̸ te_|
|Australian|46.38|87.29|36.20|86.38|10.17|0.91|46.50|87.15|-0.12|0.14|
|Bands|53.22|73.53|52.20|72.80|1.02|0.73|58.20|73.46|-4.98|0.07|
|Bupa|152.76|72.13|187.20|68.09|-34.44|4.04|181.19|72.38|-28.44|-0.25|
|Dermatology|215.64|96.55|198.05|96.07|17.58|0.48|182.84|94.40|32.80|2.15|
|Glass|403.08|73.09|343.60|72.09|59.49|1.00|474.29|72.24|-71.20|0.85|
|Haberman|9.00|77.11|10.20|75.76|-1.20|1.35|10.80|77.40|-1.80|-0.29|
|Heart|105.16|83.95|122.72|84.44|-17.56|-0.49|123.29|84.57|-18.13|-0.62|
|Ionosphere|58.29|93.18|90.33|90.22|-32.04|2.96|88.03|91.56|-29.73|1.62|
|Iris|30.35|98.67|26.29|96.00|4.06|2.67|30.37|97.33|-0.02|1.34|
|Mammogr.|50.57|84.35|92.25|84.20|-41.69|0.15|73.84|84.20|-23.27|0.15|
|Pima|57.65|77.28|60.89|76.18|-3.24|1.10|56.12|77.01|1.53|0.27|
|Saheart|59.40|72.23|86.75|69.33|-27.35|2.90|59.28|70.05|0.12|2.18|
|Sonar|64.62|79.29|79.76|76.80|-15.14|2.49|49.31|78.61|15.31|0.68|
|Vehicle|236.17|68.20|242.79|67.62|-6.62|0.58|195.07|68.20|41.10|0.00|
|Wdbc|47.35|96.31|37.35|96.96|10.00|-0.65|25.04|96.78|22.31|-0.47|
|Wine|34.00|99.61|35.82|98.30|-1.82|1.31|40.39|98.49|-6.39|1.12|
|Wisconsin|49.85|96.99|74.36|96.74|-24.51|0.25|69.81|96.95|-19.96|0.04|
|**Mean**|**98.44**|**84.10**|**104.52**|**82.82**|||**103.79**|**83.58**|||



_Table 6_ . The comparison result of the accuracy of HABR-MUL, HATRI and HATRA classifiers using the Wilcoxon signed rank test at level _α_ = 0.05 

|**VS**|**R**<sup>+</sup>|**R**<sup>_−_</sup>|**E.** **_P_-value**|**A.** **_P_-value**|**Hypothesis**|
|---|---|---|---|---|---|
|HABR-MUL vs HATRI|143.0|10.0|6.562E-4|0.001516|Rejected|
|HABR-MUL vs HATRA|107.0|29.0|0.04432|0.041102|Rejected|



To make sure the differences are significant, Wilcoxon’s signed-rank test at level _α_ = 0.05 is used to test the equivalent hypotheses. As shown in the Table 6, all _p-values_ are less than _α_ = 0.05, all _null-hypotheses_ are rejected. In the Table 7, all _p-values_ are greater than _α_ = 0.05, all _null-hypotheses_ are not rejected. Thus, we can state that the HABR-MUL has better classification accuracy than HATRI and HATRA while the complexities of the fuzzy rule bases are equivalent. 

332 

PHAM DINH PHONG et al. 

_Table 7_ . The comparison result of the complexity of HABR-MUL, HATRI and HATRA classifiers using the Wilcoxon signed rank test at level _α_ = 0.05 

|**VS**|**R**<sup>+</sup>|**R**<sup>_−_</sup>|**E.** **_P_-value**|**A.** **_P_-value**|**Hypothesis**|
|---|---|---|---|---|---|
|HABR-MUL vs HATRI|104.0|49.0|_≥_0_._2|0.185016|Not rejected|
|HABR-MUL vs HATRA|97.0|56.0|_≥_0_._2|0.320174|Not rejected|



## **3.3. The proposed classifier versus the fuzzy set theory based classifiers** 

To show more about the efficiency of the proposed classifier, we run a comparison study of the proposed classifier with existing fuzzy rule based classifiers examined by M. Antonelli et al. 2014 so-called PAES-RCS in conjunction with non-evolutionary classification algorithms so-called FURIA [2]. 

_Table 8_ . The experimental results of the HABR-MUL, the PAES-RCS and the FURIA classifiers 

|**Dataset**|**HABR-**<br>|**MUL**<br>|**PAES-R**<br>|**CS**<br>|_̸_=_R×C_|_̸_=_P te_|**FURIA**<br>||_̸_=_R×C_|_̸_=_P te_|
|---|---|---|---|---|---|---|---|---|---|---|
||#_R×#C_|_Tte_|#_R×#C_|_Tte_|_̸_|_̸ _|#_R×#C_|_Tte_|_̸_|_̸ _|
|Australian|46.38|87.29|329.64|85.80|-283.26|1.49|89.60|85.22|-43.22|2.07|
|Bands|53.22|73.53|756.00|67.56|-702.78|5.97|535.15|64.65|-481.93|8.88|
|Bupa|152.76|72.13|256.20|68.67|-103.44|3.46|324.12|69.02|-171.36|3.11|
|Dermatology|215.64|96.55|389.40|95.43|-173.76|1.12|303.88|95.24|-88.24|1.31|
|Glass|403.08|73.09|487.90|72.13|-84.82|0.96|474.81|72.41|-71.73|0.68|
|Haberman|9.00|77.11|202.41|72.65|-193.41|4.46|22.04|75.44|-13.04|1.67|
|Heart|105.16|83.95|300.30|83.21|-195.14|0.74|193.64|80.00|-88.48|3.95|
|Ionosphere|58.29|93.18|670.63|90.40|-612.34|2.78|372.68|91.75|-314.39|1.43|
|Iris|30.35|98.67|69.84|95.33|-39.49|3.34|31.95|94.66|-1.60|4.01|
|Mammogr.|50.57|84.35|132.54|83.37|-81.97|0.98|16.83|83.89|33.74|0.46|
|Pima|57.65|77.28|270.64|74.66|-212.99|2.62|127.50|74.62|-69.85|2.66|
|Saheart|59.40|72.23|525.21|70.92|-465.81|1.31|50.88|69.69|8.52|2.54|
|Sonar|64.62|79.29|524.60|77.00|-459.98|2.29|309.96|82.14|-245.34|_−_2_._85|
|Vehicle|236.17|68.20|555.77|64.89|-319.60|3.31|2125.97|71.52|-1889.80|-3.32|
|Wdbc|47.35|96.31|183.70|95.14|-136.35|1.17|356.12|96.31|-308.77|0.00|
|Wine|34.00|99.61|170.94|93.98|-136.94|5.63|80.00|96.60|-46.00|3.01|
|Wisconsin|49.85|96.99|328.02|96.46|-278.17|0.53|521.10|96.35|-471.25|0.64|
|**Mean**|**98.44**|**84.10**|**361.98**|**81.62**|||**349.19**|**82.32**|||



_Table 9_ . The comparison result of the accuracy of HABR-MUL, PAES-RCS and FURIA classifiers using the Wilcoxon signed rank test at level _α_ = 0.05 

|**VS**|**R**<sup>+</sup>|**R**<sup>_−_</sup>|**E.** **_P_-value**|**A.** **_P_-value**|**Hypothesis**|
|---|---|---|---|---|---|
|HABR-MUL vs PAES-RCS|153.0|0.0|1.5258E-5|0.000267|Rejected|
|HABR-MUL vs FURIA|113.0|23.0|0.01825|0.018635|Rejected|



PAES-RCS [2] is a multi-objective evolutionary approach deployed to learn concurrently the fuzzy rule bases and databases of FRBCs. It exploits the pre-specified granularity of each attribute for generating the candidate fuzzy set by applying the C4.5 algorithm [32]. Then, 

333 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 

_Table 10_ . The comparison result of the complexity of the HABR-MUL, the PAES-RCS and the FURIA classifiers using the Wilcoxon signed rank test at level _α_ = 0.05 

|**VS**|**R**<sup>+</sup>|**R**<sup>_−_</sup>|**E.** **_P_-value**|**A.** **_P_-value**|**Hypothesis**|
|---|---|---|---|---|---|
|HABR-MUL vs PAES-RCS|153.0|0.0|1.5258E-5|0.000267|Rejected|
|HABR-MUL vs FURIA|147.0|6.0|2.136E-4|0.000777|Rejected|



the multi-objective evolutionary process is performed to select a set of fuzzy rules from the candidate rule set in conjunction with a set of conditions for each selected rule, named as the rule and condition selection (RCS). The membership functions of linguistic terms are concurrently learned during the RCS process. 

The comparison of the classification accuracies on test sets and the complexities between the proposed classifier and the two other classifiers PAES-RCS and FURIA are shown in the Table 8. The HABR-MUL has better classification accuracies and better classifier complexities than PAES-RCS on all test datasets. HABR-MUL has better classification accuracies and better classifier complexities than FURIA on 15 of 17 test datasets. Based on mean values of the classification accuracies and the classifier complexities, the proposed classifier is much better than PAES-RCS and FURIA on both classification accuracy and complexity measures. To make sure the differences are significant, Wilcoxon’s signed-rank test at level _α_ = 0.05 is used to test the equivalent hypotheses. As shown in the Table 9 and the Table 10, since all _p-values_ are less than _α_ = 0.05, all _null-hypotheses_ are rejected. Thus, we can state that the proposed classifier strictly outperforms PAES-RCS and FURIA classifiers. 

## **4. CONCLUSIONS** 

Fuzzy rule based systems which deal with uncertainty information have been applied successfully in solving the FRBC design problem. There is the fact that although fuzzy rule bases are represented by linguistic terms associated with their fuzzy set based semantics, the problem of the linguistic term design is not clearly studied in the fuzzy set theory approaches. HAs provide a mathematical formalism of term design so that the fuzzy set based semantics of all linguistic terms are generated from qualitative semantics of terms. So far, the FRBCs design based on hedge algebra approach generate fuzzy rule bases with fuzzy sets based semantics of linguistic terms for classifiers. This paper presents a pure hedge algebra based classifier design methodology which generates fuzzy rule based classifiers with the semantics of the linguistic terms in the fuzzy rule bases are the hedge algebras based semantics. To do so, a hedge algebra based classification reasoning with multi-granularity fuzzy partitioning method is applied for data classification. The new classification reasoning method enables fuzzy sets based semantics of linguistic terms in fuzzy rule bases of classifiers to be replaced with hedge algebra based semantics. Experimental results on 17 real world datasets have shown that the multi-granularity structure is more efficient than the single granularity structure and the proposed classifier outperforms the existing ones. By research results of this paper, we can state that fuzzy rule based classifiers can be designed purely based on hedge algebras based semantics of linguistic terms. 

334 

PHAM DINH PHONG et al. 

## **5. ACKNOWLEDGMENT** 

This research is funded by Vietnam National Foundation for Science and Technology Development (NAFOSTED) under Grant No. 102.01-2017.06. 

## **REFERENCES** 

- [1] R. Alcal, Y. Nojima, F. Herrera, and H. Ishibuchi, “Multiobjective genetic fuzzy rule selection of single granularity-based fuzzy classification rules and its interaction with the lateral tuning of membership functions,” _Soft Computing_ , vol. 15, no. 12, pp. 2303–2318, 2011. 

- [2] M. Antonelli, P. Ducange, and F. Marcelloni, “A fast and efficient multi-objective evolutionary learning scheme for fuzzy rule-based classifiers,” _Information Sciences_ , vol. 283, pp. 36–54, 2014. 

- [3] C. J. C. Burges, “A tutorial on support vector machines for pattern recognition,” in _Proceedings of Int Conference on Data Mining and Knowledge Discovery_ , vol. 2, no. 2. Boston. Manufactured in The Netherlands: Kluwer Academic Publishers, 1998, pp. 121–167. 

- [4] J. Demar, “Statistical comparisons of classifiers over multiple data sets,” _The Journal of Machine Learning Research_ , vol. 7, pp. 1–30, 2006. 

- [5] D. K. Dong, T. D. Khang, and D. K. Dung, “Fuzzy clustering with hedge algebra,” in _Proceedings of the 2010 Symposium on Information and Communication Technology_ , Hanoi, Vietnam, 2010, pp. 49–54. 

- [6] M. Elkano, M. Galar, J. Sanz, and H. Bustince, “Chi-bd: A fuzzy rule-based classification system for big data classification problems,” _Fuzzy Sets and Systems_ , vol. 348, pp. 75–101, 2018. 

- [7] M. Fazzolari, R. Alcal, and F. Herrera, “A multi-objective evolutionary method for learning granularities based on fuzzy discretization to improve the accuracy-complexity trade-off of fuzzy rule-based classification systems: D-mofarc algorithm,” _Applied Soft Computing_ , vol. 24, pp. 470–481, 2014. 

- [8] A. K. Ghosh, “A probabilistic approach for semi-supervised nearest neighbor classification,” _Pattern Recognition Letters_ , vol. 33, no. 9, pp. 1127–1133, 2012. 

- [9] N. C. Ho, “A topological completion of refined hedge algebras and a model of fuzziness of linguistic terms and hedges,” _Fuzzy Sets and Systems_ , vol. 158, no. 4, pp. 436–451, 2007. 

- [10] N. C. Ho, V. N. Lan, and L. X. Viet, “Optimal hedge-algebras-based controller: Design and application,” _Fuzzy Sets and Systems_ , vol. 159, no. 8, pp. 968–989, 2008. 

- [11] N. C. Ho and N. V. Long, “Fuzziness measure on complete hedges algebras and quantifying semantics of terms in linear hedge algebras,” _Fuzzy Sets and Systems_ , vol. 158, no. 4, pp. 452– 471, 2007. 

- [12] N. C. Ho, H. V. Nam, T. D. Khang, and L. H. Chau, “Hedge algebras, linguistic-valued logic and their application to fuzzy reasoning,” _Internat. J. Uncertain. Fuzziness Knowledge-Based Systems_ , vol. 7, no. 4, pp. 347–361, 1999. 

- [13] N. C. Ho, W. Pedrycz, D. T. Long, and T. T. Son, “A genetic design of linguistic terms for fuzzy rule based classifiers,” _International Journal of Approximate Reasoning_ , vol. 54, no. 1, pp. 1–21, 2013. 

335 

A HEDGE ALGEBRAS BASED CLASSIFICATION REASONING METHOD 

- [14] N. C. Ho, T. T. Son, T. D. Khang, and L. X. Viet, “Fuzziness measure, quantified semantic mapping and interpolative method of approximate reasoning in medical expert systems,” _Journal of Computer Science and Cybernetics_ , vol. 18, no. 3, pp. 237–252, 2002. 

- [15] N. C. Ho, T. T. Son, and P. D. Phong, “Modeling of a semantics core of linguistic terms based on an extension of hedge algebra semantics and its application,” _Knowledge-Based Systems_ , vol. 67, pp. 244–262, 2014. 

- [16] N. C. Ho, H. V. Thong, and N. V. Long, “A discussion on interpretability of linguistic rule based systems and its application to solve regression problems,” _Knowledge-Based Systems_ , vol. 88, pp. 107–133, 2015. 

- [17] N. C. Ho and W. Wechler, “Hedge algebras: an algebraic approach to structures of sets of linguistic domains of linguistic truth values,” _Fuzzy Sets and Systems_ , vol. 35, pp. 281–293, 1990. 

- [18] ——, “Extended algebra and their application to fuzzy logic,” _Fuzzy Sets and Systems_ , vol. 52, no. 3, pp. 259–281, 1992. 

- [19] L. N. Hung and V. M. Loc, “Primacy of fuzzy relational databases based on hedge algebras,” in _Volume 144 of the series Lecture Notes of the Institute for Computer Sciences, Social Informatics and Telecommunications Engineering_ . Ho Chi Minh City, Vietnam: Springer, Cham, 2015, pp. 292–305. 

- [20] N. H. Huy, N. C. Ho, and N. V. Quyen, “Multichannel image contrast enhancement based on linguistic rule-based intensificators,” _Applied Soft Computing Journal_ , vol. 76, pp. 744–762, 2019. 

- [21] H. Ishibuchi and Y. Nojima, “Analysis of interpretability-accuracy tradeoff of fuzzy systems by multi-objective fuzzy genetics-based machine learning,” _International Journal of Approximate Reasoning_ , vol. 44, pp. 4–31, 2007. 

- [22] H. Ishibuchi, K. Nozaki, and H. Tanaka, “Distributed representation of fuzzy rules and its application to pattern classification,” _Fuzzy Sets and Systems_ , vol. 52, no. 1, pp. 21–32, 1992. 

- [23] H. Ishibuchi and T. Yamamoto, “Fuzzy rule selection by multi-objective genetic local search algorithms and rule evaluation measures in data mining,” _Fuzzy Sets and Systems_ , vol. 141, no. 1, pp. 59–88, 2004. 

- [24] ——, “Rule weight specification in fuzzy rule-based classification systems,” _IEEE Transactions on Fuzzy Systems_ , vol. 13, no. 4, pp. 428–435, 2005. 

- [25] L. V. T. Lan, N. M. Han, and N. C. Hao, “An algorithm to build a fuzzy decision tree for data classification problem based on the fuzziness intervals matching,” _Journal of Computer Science and Cybernetics_ , vol. 32, no. 4, pp. 367–380, 2016. 

- [26] V. N. Lan, T. T. Ha, P. K. Lai, and N. T. Duy, “The application of the hedge algebras in forecast control based on the models,” in _In Proceedings of The 11st National Conference on Fundamental and Applied IT Research_ , Hanoi, Vietnam, 2018, pp. 521–528. 

- [27] H. Langseth and T. D. Nielsen, “Classification using hierarchical na¨ıve bayes models,” _Machine Learning_ , vol. 63, no. 2, pp. 135–159, 2006. 

- [28] B. H. Le, L. T. Anh, and B. V. Binh, “Explicit formula of hedge-algebras-based fuzzy controller and applications in structural vibration control,” _Applied Soft Computing_ , vol. 60, pp. 150–166, 2017. 

336 

PHAM DINH PHONG et al. 

- [29] B. H. Le, N. C. Ho, V. N. Lan, and N. C. Hung, “General design method of hedge-algebras-based fuzzy controllers and an application for structural active control,” _Applied Intelligence_ , vol. 43, no. 2, pp. 251–275, 2015. 

- [30] M. S. Lechuga, “Multi-objective optimization using sharing in swarm optimization algorithms,” 2016. 

- [31] D. T. Long, “A genetic algorithm based method for timetabling problems using linguistics of hedge algebra in constraints,” _Journal of Computer Science and Cybernetics_ , vol. 32, no. 4, pp. 285–301, 2016. 

- [32] M. M. Mazid, M. M. Mazid, and K. S. Tickle, “Improved c4.5 algorithm for rule based classification,” in _Proceedings of the 9th WSEAS International Conference on Artificial Intelligence, Knowledge Engineering and Databases_ , University of Cambridge, UK, 2010, pp. 296–301. 

- [33] D. Nauck and R. Kruse, “Nefclass: A neuro-fuzzy approach for the classification of data,” in _Proceedings of the 1995 ACM symposium on Applied computing_ , Nashville, TN, 1995, pp. 461– 465. 

- [34] P. D. Phong, N. C. Ho, and N. T. Thuy, “Multi-objective particle swarm optimization algorithm and its application to the fuzzy rule based classifier design problem with the order based semantics of linguistic terms,” in _In Proceedings of The 10th IEEE RIVF International Conference on Computing and Communication Technologies (RIVF-2013)_ , Hanoi, Vietnam, 2013, pp. 12–17. 

- [35] M. Pota, M. Esposito, and G. D. Pietro, “Designing rule-based fuzzy systems for classification in medicine,” _Knowledge-Based Systems_ , vol. 124, pp. 105–132, 2017. 

- [36] M. I. Rey, M. Galende, M. J. Fuente, and G. I. Sainz-Palmero, “Multi-objective based fuzzy rule based systems (frbss) for trade-off improvement in accuracy and interpretability: A rule relevance point of view,” _Knowledge-Based Systems_ , vol. 127, pp. 67–84, 2017. 

- [37] S.-B. Roh, W. Pedrycz, and T.-C. Ahn, “A design of granular fuzzy classifier,” _Expert Systems with Applications_ , vol. 41, pp. 6786–6795, 2014. 

- [38] F. Rudziski, “A multi-objective genetic optimization of interpretability-oriented fuzzy rule-based classifiers,” _Applied Soft Computing_ , vol. 38, pp. 118–133, 2016. 

- [39] J. Sanz, A. Fernndez, H. Bustince, and F. Herrera, “A genetic tuning to improve the performance of fuzzy rule-based classification systems with interval-valued fuzzy sets: Degree of ignorance and lateral position,” _International Journal of Approximate Reasoning_ , vol. 52, no. 6, pp. 751–766, 2011. 

- [40] T. T. Son and N. T. Anh, “Partition fuzzy domain with multi-granularity representation of data based on hedge algebra approach,” _Journal of Computer Science and Cybernetics_ , vol. 34, no. 1, pp. 63–75, 2018. 

- [41] M. Soui, I. Gasmi, S. Smiti, and K. Ghdira, “Rule-based credit risk assessment model using multi-objective evolutionary algorithms,” _Expert Systems with Applications_ , vol. 126, pp. 144– 157, 2019. 

- [42] D. V. Thang and D. V. Ban, “Query data with fuzzy information in object-oriented databases an approach the semantic neighborhood of hedge algebras,” _International Journal of Computer Science and Information Security_ , vol. 9, no. 5, pp. 37–42, 2011. 

_Received on August 22, 2019 Revised on October 03, 2019_ 

