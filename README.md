units lj
atom_style atomic
boundary p p p
lattice fcc 0.8442
region box block 0 10 0 10 0 10
create_box 2 box
variable methane_atoms equal 300
variable pentane_atoms equal 300
create_atoms 1 random ${methane_atoms} 12345 box
create_atoms 2 random ${pentane_atoms} 54321 box
mass 1 16.043  # methane
mass 2 72.15   # pentane
pair_style lj/cut 2.5
pair_coeff 1 1 1.0 1.0 3.74
pair_coeff 2 2 1.0 1.0 5.282
write_data init_50_50.data
units lj
atom_style atomic
boundary p p p
lattice fcc 0.8442
region box block 0 10 0 10 0 10
create_box 2 box
variable methane_atoms equal 450
variable pentane_atoms equal 150
create_atoms 1 random ${methane_atoms} 12345 box
create_atoms 2 random ${pentane_atoms} 54321 box
mass 1 16.043  # methane
mass 2 72.15   # pentane
pair_style lj/cut 2.5
pair_coeff 1 1 1.0 1.0 3.74
pair_coeff 2 2 1.0 1.0 5.282
write_data init_75_25.data
units lj
atom_style atomic
boundary p p p
lattice fcc 0.8442
region box block 0 10 0 10 0 10
create_box 2 box
variable methane_atoms equal 150
variable pentane_atoms equal 450
create_atoms 1 random ${methane_atoms} 12345 box
create_atoms 2 random ${pentane_atoms} 54321 box
mass 1 16.043  # methane
mass 2 72.15   # pentane
pair_style lj/cut 2.5
pair_coeff 1 1 1.0 1.0 3.74
pair_coeff 2 2 1.0 1.0 5.282
write_data init_25_75.data
lmp_mpi -in init_25_75.in
lmp_mpi -in init_50_50.in
lmp_mpi -in init_75_25.in



