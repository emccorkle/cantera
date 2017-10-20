cmake_minimum_required(VERSION 3.5.0)

# Collect sources
set(sources latsol.cpp)
set(resources Li_Liquid.xml
              Li7Si3_ls.xml
              LiKCl_liquid.xml
              output_blessed.txt
              verbose_blessed.txt)

# Setup executable
add_executable(VCSnonideal_LatticeSolid_LiSi ${sources} ${resources})
target_link_libraries(VCSnonideal_LatticeSolid_LiSi cantera)
