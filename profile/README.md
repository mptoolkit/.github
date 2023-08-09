## Matrix Product Toolkit

This is the code repository for the Matrix Product Toolkit.

The public code repository is at https://github.com/mptoolkit/mptoolkit

Documentation is at https://mptoolkit.qusim.net/

The toolkit is a software suite of tools for creating and manipulating Matrix Product States, which is a form of Tensor Network.

Tensor Networks provide a theoretical framework that captures the important properties of quantum systems (such as entanglement) in a way that also allows use of algebraic properties such as geometric and internal symmetries. The result is a framework for computational methods that combines powerful algebraic methods with efficient numerical techniques that can make good use of modern computational architectures (such as GPU devices) to give tools for modelling many-body quantum systems at a microscopic level. These tools have many applications, from fundamental physics such as the classification of topological states of matter, to applications in real materials and devices such as ultra-cold atomic gases and quantum-engineered devices.

In one-dimension, tensor networks have a quite long history, via the density-matrix renormalization-group (DMRG) algorithm developed by Steven R White in 1992. While the method was originally formulated slightly differently, it quickly* became apparent that DMRG is built around a one-dimensional tensor network, which is known as a Matrix Product State (MPS).

The Matrix Product Toolkit is a project which started life around 2002, originally envisaged as a ‘next generation’ DMRG code, incorporating non-abelian symmetries[1] and with an emphasis on a flexible and generic way to construct Hamiltonian operators and measure observables.

In 2003/2004 there were a lot of developments connecting DMRG and Matrix Product States, many of which were discussed at the workshop “Recent Progress and Prospects in DMRG”, held in Leiden in 2004. Especially with the advent of TEBD / t-DMRG it made sense to construct a software toolkit using the MPS representation, and covering a wide range of tools (groundstates, real-time evolution, frequency space methods, etc). Around this time, I realized that the ‘generic’ way to construct a Hamiltonian that I was working on for DMRG was exactly the form of a Matrix Product Operator, and thus the Matrix Product Toolkit was born.

Since then the toolkit has grown to around 100,000 lines of C++. It is currently split into two versions, the ‘old’ toolkit for finite-size calculations (accessed via svn), and a ‘new’ version, which started out as a branch for infinite-DMRG, but ultimately there were enough changes to the underlying code that merging the two branches was impractical. Instead, individual tools from the ‘old’ toolkit are getting ported to the new version as the need arises. The aim is to combine, in a single toolkit, finite[2], infinite[3], IBC[4], Excitation Ansatz[5] tools, with as much code reuse as possible.

The toolkit has been used in over 100 research papers since its development. It isn’t formally described in a research publication as such, however a simple acknowledgement and citation of this Toolkit website (and, when it appears, the Toolkit publication) is sufficient.

[1] *The non-Abelian density matrix renormalization group algorithm*, I. P. McCulloch and M. Gulácsi, EPL 57 852 (2002), https://doi.org/10.1209/epl/i2002-00393-0

[2] *From density-matrix renormalization group to matrix product states*, Ian P McCulloch J. Stat. Mech. (2007) P10014, https://doi.org/10.1088/1742-5468/2007/10/P10014

[3] *Infinite size density matrix renormalization group, revisited*, I. P. McCulloch, https://doi.org/10.48550/arXiv.0804.2509

[4] *Infinite boundary conditions for matrix product state calculations*, Ho N. Phien, Guifre Vidal, Ian P. McCulloch, Phys. Rev. B 86, 245107 (2012)  https://doi.org/10.1103/PhysRevB.86.245107

[5] *Variational matrix product ansatz for dispersion relations*, Jutho Haegeman, Bogdan Pirvu, David J. Weir, J. Ignacio Cirac, Tobias J. Osborne, Henri Verschelde, and Frank Verstraete, Phys. Rev. B 85, 100408(R) (2012), https://doi.org/10.1103/PhysRevB.85.100408

[*] Actually, although a key publication came relatively early, with "Thermodynamic Limit of Density Matrix Renormalization", Stellan Östlund and Stefan Rommer, Phys. Rev. Lett. 75, 3537 https://doi.org/10.1103/PhysRevLett.75.3537 , it took several more years for these ideas to develop. In practice, the correspondence between DMRG and MPS is less clear in the sense that the programming structures of the methods are somewhat different, and have different trade-offs in terms of computational efficiency.
