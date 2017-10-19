cmake_minimum_required(VERSION 3.5.0)

# Setup includes
set(include_dir ${CMAKE_CURRENT_SOURCE_DIR}/../include)
set(include_cantera_dir ${include_dir}/cantera)

# Accumulate sources
set(root_includes ${include_cantera_dir}/Edge.h
                  ${include_cantera_dir}/IdealGasMix.h
                  ${include_cantera_dir}/IncompressibleSolid.h
                  ${include_cantera_dir}/Interface.h
                  ${include_cantera_dir}/kinetics.h
                  ${include_cantera_dir}/Metal.h
                  ${include_cantera_dir}/onedim.h
                  ${include_cantera_dir}/PureFluid.h
                  ${include_cantera_dir}/reactionpaths.h
                  ${include_cantera_dir}/thermo.h
                  ${include_cantera_dir}/transport.h
                  ${include_cantera_dir}/zerodim.h)

set(base_sources base/AnyMap.cpp
                 base/application.cpp
                 base/application.h
                 base/checkFinite.cpp
                 base/clockWC.cpp
                 base/ct2ctml.cpp
                 base/ctexceptions.cpp
                 base/ctml.cpp
                 base/global.cpp
                 base/plots.cpp
                 base/stringUtils.cpp
                 base/units.h
                 base/ValueCache.cpp
                 base/xml.cpp)

set(base_includes ${include_cantera_dir}/base/AnyMap.h
                  ${include_cantera_dir}/base/Array.h
                  ${include_cantera_dir}/base/clockWC.h
                  ${include_cantera_dir}/base/config.h
                  ${include_cantera_dir}/base/config.h.in
                  ${include_cantera_dir}/base/ct_defs.h
                  ${include_cantera_dir}/base/ctexceptions.h
                  ${include_cantera_dir}/base/ctml.h
                  ${include_cantera_dir}/base/FactoryBase.h
                  ${include_cantera_dir}/base/fmt.h
                  ${include_cantera_dir}/base/global.h
                  ${include_cantera_dir}/base/logger.h
                  ${include_cantera_dir}/base/plots.h
                  ${include_cantera_dir}/base/stringUtils.h
                  ${include_cantera_dir}/base/utilities.h
                  ${include_cantera_dir}/base/ValueCache.h
                  ${include_cantera_dir}/base/xml.h)

set(clib_sources clib/Cabinet.h
                 clib/clib_utils.h
                 clib/ct.cpp
                 clib/ctfunc.cpp
                 clib/ctmultiphase.cpp
                 clib/ctonedim.cpp
                 clib/ctreactor.cpp
                 clib/ctrpath.cpp
                 clib/ctsurf.cpp
                 clib/ctxml.cpp
                 clib/README.txt)

set(clib_includes ${include_cantera_dir}/clib/clib_defs.h
                  ${include_cantera_dir}/clib/ct.h
                  ${include_cantera_dir}/clib/ctfunc.h
                  ${include_cantera_dir}/clib/ctmatlab.h
                  ${include_cantera_dir}/clib/ctmultiphase.h
                  ${include_cantera_dir}/clib/ctonedim.h
                  ${include_cantera_dir}/clib/ctreactor.h
                  ${include_cantera_dir}/clib/ctrpath.h
                  ${include_cantera_dir}/clib/ctsurf.h
                  ${include_cantera_dir}/clib/ctxml.h)

set(cython_includes ${include_cantera_dir}/cython/funcWrapper.h
                    ${include_cantera_dir}/cython/wrappers.h)

set(equil_sources equil/BasisOptimize.cpp
                  equil/ChemEquil.cpp
                  equil/MultiPhase.cpp
                  equil/MultiPhaseEquil.cpp
                  equil/vcs_elem.cpp
                  equil/vcs_elem_rearrange.cpp
                  equil/vcs_Gibbs.cpp
                  equil/vcs_inest.cpp
                  equil/vcs_MultiPhaseEquil.cpp
                  equil/vcs_phaseStability.cpp
                  equil/vcs_prep.cpp
                  equil/vcs_prob.cpp
                  equil/vcs_report.cpp
                  equil/vcs_rxnadj.cpp
                  equil/vcs_setMolesLinProg.cpp
                  equil/vcs_solve.cpp
                  equil/vcs_solve_TP.cpp
                  equil/vcs_species_thermo.cpp
                  equil/vcs_SpeciesProperties.cpp
                  equil/vcs_TP.cpp
                  equil/vcs_util.cpp
                  equil/vcs_VolPhase.cpp)

set(equil_includes ${include_cantera_dir}/equil/ChemEquil.h
                   ${include_cantera_dir}/equil/MultiPhase.h
                   ${include_cantera_dir}/equil/MultiPhaseEquil.h
                   ${include_cantera_dir}/equil/vcs_defs.h
                   ${include_cantera_dir}/equil/vcs_internal.h
                   ${include_cantera_dir}/equil/vcs_MultiPhaseEquil.h
                   ${include_cantera_dir}/equil/vcs_solve.h
                   ${include_cantera_dir}/equil/vcs_species_thermo.h
                   ${include_cantera_dir}/equil/vcs_SpeciesProperties.h
                   ${include_cantera_dir}/equil/vcs_VolPhase.h)

set(fortran_sources fortran/cantera.f90
                    fortran/cantera_funcs.f90
                    fortran/cantera_iface.f90
                    fortran/cantera_kinetics.f90
                    fortran/cantera_thermo.f90
                    fortran/cantera_transport.f90
                    fortran/cantera_xml.f90
                    fortran/fct.cpp
                    fortran/fct_interface.f90
                    fortran/fctxml.cpp
                    fortran/fctxml_interface.f90
                    fortran/SConscript)

set(kinetics_sources kinetics/AqueousKinetics.cpp
                     kinetics/BulkKinetics.cpp
                     kinetics/Falloff.cpp
                     kinetics/FalloffFactory.cpp
                     kinetics/GasKinetics.cpp
                     kinetics/Group.cpp
                     kinetics/ImplicitSurfChem.cpp
                     kinetics/importKinetics.cpp
                     kinetics/InterfaceKinetics.cpp
                     kinetics/Kinetics.cpp
                     kinetics/KineticsFactory.cpp
                     kinetics/Reaction.cpp
                     kinetics/ReactionPath.cpp
                     kinetics/RxnRates.cpp
                     kinetics/solveSP.cpp)

set(kinetics_includes ${include_cantera_dir}/kinetics/AqueousKinetics.h
                      ${include_cantera_dir}/kinetics/BulkKinetics.h
                      ${include_cantera_dir}/kinetics/EdgeKinetics.h
                      ${include_cantera_dir}/kinetics/Falloff.h
                      ${include_cantera_dir}/kinetics/FalloffFactory.h
                      ${include_cantera_dir}/kinetics/FalloffMgr.h
                      ${include_cantera_dir}/kinetics/GasKinetics.h
                      ${include_cantera_dir}/kinetics/Group.h
                      ${include_cantera_dir}/kinetics/ImplicitSurfChem.h
                      ${include_cantera_dir}/kinetics/importKinetics.h
                      ${include_cantera_dir}/kinetics/InterfaceKinetics.h
                      ${include_cantera_dir}/kinetics/Kinetics.h
                      ${include_cantera_dir}/kinetics/KineticsFactory.h
                      ${include_cantera_dir}/kinetics/RateCoeffMgr.h
                      ${include_cantera_dir}/kinetics/Reaction.h
                      ${include_cantera_dir}/kinetics/reaction_defs.h
                      ${include_cantera_dir}/kinetics/ReactionPath.h
                      ${include_cantera_dir}/kinetics/RxnRates.h
                      ${include_cantera_dir}/kinetics/solveSP.h
                      ${include_cantera_dir}/kinetics/StoichManager.h
                      ${include_cantera_dir}/kinetics/ThirdBodyCalc.h)

set(matlab_sources matlab/.gitignore
                   matlab/ctfunctions.cpp
                   matlab/ctmatutils.h
                   matlab/ctmethods.cpp
                   matlab/flowdevicemethods.cpp
                   matlab/funcmethods.cpp
                   matlab/kineticsmethods.cpp
                   matlab/mexFunction.map
                   matlab/mixturemethods.cpp
                   matlab/mllogger.h
                   matlab/onedimmethods.cpp
                   matlab/phasemethods.cpp
                   matlab/reactormethods.cpp
                   matlab/reactornetmethods.cpp
                   matlab/reactorsurfacemethods.cpp
                   matlab/SConscript
                   matlab/surfmethods.cpp
                   matlab/thermomethods.cpp
                   matlab/transportmethods.cpp
                   matlab/wallmethods.cpp
                   matlab/xmlmethods.cpp)

set(numerics_sources numerics/BandMatrix.cpp
                     numerics/CVodesIntegrator.cpp
                     numerics/DAE_solvers.cpp
                     numerics/DenseMatrix.cpp
                     numerics/Func1.cpp
                     numerics/FuncEval.cpp
                     numerics/funcs.cpp
                     numerics/IDA_Solver.cpp
                     numerics/ODE_integrators.cpp
                     numerics/polyfit.cpp
                     numerics/ResidJacEval.cpp)

set(numerics_includes ${include_cantera_dir}/numerics/BandMatrix.h
                      ${include_cantera_dir}/numerics/ctlapack.h
                      ${include_cantera_dir}/numerics/CVodesIntegrator.h
                      ${include_cantera_dir}/numerics/DAE_Solver.h
                      ${include_cantera_dir}/numerics/DenseMatrix.h
                      ${include_cantera_dir}/numerics/eigen_dense.h
                      ${include_cantera_dir}/numerics/Func1.h
                      ${include_cantera_dir}/numerics/FuncEval.h
                      ${include_cantera_dir}/numerics/funcs.h
                      ${include_cantera_dir}/numerics/GeneralMatrix.h
                      ${include_cantera_dir}/numerics/IDA_Solver.h
                      ${include_cantera_dir}/numerics/Integrator.h
                      ${include_cantera_dir}/numerics/polyfit.h
                      ${include_cantera_dir}/numerics/ResidEval.h
                      ${include_cantera_dir}/numerics/ResidJacEval.h)

set(oned_sources oneD/boundaries1D.cpp
                 oneD/Domain1D.cpp
                 oneD/IonFlow.cpp
                 oneD/MultiJac.cpp
                 oneD/MultiNewton.cpp
                 oneD/OneDim.cpp
                 oneD/refine.cpp
                 oneD/Sim1D.cpp
                 oneD/StFlow.cpp)

set(oned_includes ${include_cantera_dir}/oneD/Domain1D.h
                  ${include_cantera_dir}/oneD/Inlet1D.h
                  ${include_cantera_dir}/oneD/IonFlow.h
                  ${include_cantera_dir}/oneD/MultiJac.h
                  ${include_cantera_dir}/oneD/MultiNewton.h
                  ${include_cantera_dir}/oneD/OneDim.h
                  ${include_cantera_dir}/oneD/refine.h
                  ${include_cantera_dir}/oneD/Sim1D.h
                  ${include_cantera_dir}/oneD/StFlow.h)

set(pch_sources pch/system.cpp
                pch/system.h)

set(thermo_sources thermo/ConstCpPoly.cpp
                   thermo/ConstDensityThermo.cpp
                   thermo/DebyeHuckel.cpp
                   thermo/Elements.cpp
                   thermo/FixedChemPotSSTP.cpp
                   thermo/GibbsExcessVPSSTP.cpp
                   thermo/HMWSoln.cpp
                   thermo/IdealGasPhase.cpp
                   thermo/IdealMolalSoln.cpp
                   thermo/IdealSolidSolnPhase.cpp
                   thermo/IdealSolnGasVPSS.cpp
                   thermo/IonsFromNeutralVPSSTP.cpp
                   thermo/LatticePhase.cpp
                   thermo/LatticeSolidPhase.cpp
                   thermo/MargulesVPSSTP.cpp
                   thermo/MaskellSolidSolnPhase.cpp
                   thermo/MetalSHEelectrons.cpp
                   thermo/MineralEQ3.cpp
                   thermo/MixedSolventElectrolyte.cpp
                   thermo/MixtureFugacityTP.cpp
                   thermo/MolalityVPSSTP.cpp
                   thermo/MolarityIonicVPSSTP.cpp
                   thermo/Mu0Poly.cpp
                   thermo/MultiSpeciesThermo.cpp
                   thermo/Nasa9Poly1.cpp
                   thermo/Nasa9PolyMultiTempRegion.cpp
                   thermo/NasaPoly2.cpp
                   thermo/PDSS.cpp
                   thermo/PDSS_ConstVol.cpp
                   thermo/PDSS_HKFT.cpp
                   thermo/PDSS_IdealGas.cpp
                   thermo/PDSS_IonsFromNeutral.cpp
                   thermo/PDSS_SSVol.cpp
                   thermo/PDSS_Water.cpp
                   thermo/PDSSFactory.cpp
                   thermo/Phase.cpp
                   thermo/PhaseCombo_Interaction.cpp
                   thermo/PureFluidPhase.cpp
                   thermo/RedlichKisterVPSSTP.cpp
                   thermo/RedlichKwongMFTP.cpp
                   thermo/SingleSpeciesTP.cpp
                   thermo/Species.cpp
                   thermo/SpeciesThermoFactory.cpp
                   thermo/SpeciesThermoInterpType.cpp
                   thermo/StoichSubstance.cpp
                   thermo/SurfPhase.cpp
                   thermo/ThermoFactory.cpp
                   thermo/ThermoPhase.cpp
                   thermo/VPStandardStateTP.cpp
                   thermo/WaterProps.cpp
                   thermo/WaterPropsIAPWS.cpp
                   thermo/WaterPropsIAPWSphi.cpp
                   thermo/WaterSSTP.cpp)

set(thermo_includes ${include_cantera_dir}/thermo/AdsorbateThermo.h
                    ${include_cantera_dir}/thermo/ConstCpPoly.h
                    ${include_cantera_dir}/thermo/ConstDensityThermo.h
                    ${include_cantera_dir}/thermo/DebyeHuckel.h
                    ${include_cantera_dir}/thermo/EdgePhase.h
                    ${include_cantera_dir}/thermo/electrolytes.h
                    ${include_cantera_dir}/thermo/Elements.h
                    ${include_cantera_dir}/thermo/FixedChemPotSSTP.h
                    ${include_cantera_dir}/thermo/GibbsExcessVPSSTP.h
                    ${include_cantera_dir}/thermo/HMWSoln.h
                    ${include_cantera_dir}/thermo/IdealGasPhase.h
                    ${include_cantera_dir}/thermo/IdealMolalSoln.h
                    ${include_cantera_dir}/thermo/IdealSolidSolnPhase.h
                    ${include_cantera_dir}/thermo/IdealSolnGasVPSS.h
                    ${include_cantera_dir}/thermo/IonsFromNeutralVPSSTP.h
                    ${include_cantera_dir}/thermo/LatticePhase.h
                    ${include_cantera_dir}/thermo/LatticeSolidPhase.h
                    ${include_cantera_dir}/thermo/MargulesVPSSTP.h
                    ${include_cantera_dir}/thermo/MaskellSolidSolnPhase.h
                    ${include_cantera_dir}/thermo/MetalPhase.h
                    ${include_cantera_dir}/thermo/MetalSHEelectrons.h
                    ${include_cantera_dir}/thermo/MineralEQ3.h
                    ${include_cantera_dir}/thermo/MixedSolventElectrolyte.h
                    ${include_cantera_dir}/thermo/MixtureFugacityTP.h
                    ${include_cantera_dir}/thermo/MolalityVPSSTP.h
                    ${include_cantera_dir}/thermo/MolarityIonicVPSSTP.h
                    ${include_cantera_dir}/thermo/Mu0Poly.h
                    ${include_cantera_dir}/thermo/MultiSpeciesThermo.h
                    ${include_cantera_dir}/thermo/Nasa9Poly1.h
                    ${include_cantera_dir}/thermo/Nasa9PolyMultiTempRegion.h
                    ${include_cantera_dir}/thermo/NasaPoly1.h
                    ${include_cantera_dir}/thermo/NasaPoly2.h
                    ${include_cantera_dir}/thermo/PDSS.h
                    ${include_cantera_dir}/thermo/PDSS_ConstVol.h
                    ${include_cantera_dir}/thermo/PDSS_HKFT.h
                    ${include_cantera_dir}/thermo/PDSS_IdealGas.h
                    ${include_cantera_dir}/thermo/PDSS_IonsFromNeutral.h
                    ${include_cantera_dir}/thermo/PDSS_SSVol.h
                    ${include_cantera_dir}/thermo/PDSS_Water.h
                    ${include_cantera_dir}/thermo/PDSSFactory.h
                    ${include_cantera_dir}/thermo/Phase.h
                    ${include_cantera_dir}/thermo/PhaseCombo_Interaction.h
                    ${include_cantera_dir}/thermo/PureFluidPhase.h
                    ${include_cantera_dir}/thermo/RedlichKisterVPSSTP.h
                    ${include_cantera_dir}/thermo/RedlichKwongMFTP.h
                    ${include_cantera_dir}/thermo/ShomatePoly.h
                    ${include_cantera_dir}/thermo/SingleSpeciesTP.h
                    ${include_cantera_dir}/thermo/Species.h
                    ${include_cantera_dir}/thermo/SpeciesThermoFactory.h
                    ${include_cantera_dir}/thermo/SpeciesThermoInterpType.h
                    ${include_cantera_dir}/thermo/speciesThermoTypes.h
                    ${include_cantera_dir}/thermo/StoichSubstance.h
                    ${include_cantera_dir}/thermo/SurfPhase.h
                    ${include_cantera_dir}/thermo/ThermoFactory.h
                    ${include_cantera_dir}/thermo/ThermoPhase.h
                    ${include_cantera_dir}/thermo/VPStandardStateTP.h
                    ${include_cantera_dir}/thermo/WaterProps.h
                    ${include_cantera_dir}/thermo/WaterPropsIAPWS.h
                    ${include_cantera_dir}/thermo/WaterPropsIAPWSphi.h
                    ${include_cantera_dir}/thermo/WaterSSTP.h)

set(tpx_sources tpx/CarbonDioxide.cpp
                tpx/CarbonDioxide.h
                tpx/Heptane.cpp
                tpx/Heptane.h
                tpx/HFC134a.cpp
                tpx/HFC134a.h
                tpx/Hydrogen.cpp
                tpx/Hydrogen.h
                tpx/Methane.cpp
                tpx/Methane.h
                tpx/Nitrogen.cpp
                tpx/Nitrogen.h
                tpx/Oxygen.cpp
                tpx/Oxygen.h
                tpx/Sub.cpp
                tpx/utils.cpp
                tpx/Water.cpp
                tpx/Water.h)

set(tpx_includes ${include_cantera_dir}/tpx/Sub.h
                 ${include_cantera_dir}/tpx/utils.h)

set(transport_sources transport/DustyGasTransport.cpp
                      transport/GasTransport.cpp
                      transport/HighPressureGasTransport.cpp
                      transport/LiquidTranInteraction.cpp
                      transport/LiquidTransport.cpp
                      transport/LiquidTransportData.cpp
                      transport/LiquidTransportParams.cpp
                      transport/LTPspecies.cpp
                      transport/MixTransport.cpp
                      transport/MMCollisionInt.cpp
                      transport/MMCollisionInt.h
                      transport/MultiTransport.cpp
                      transport/SimpleTransport.cpp
                      transport/SolidTransport.cpp
                      transport/SolidTransportData.cpp
                      transport/TransportBase.cpp
                      transport/TransportData.cpp
                      transport/TransportFactory.cpp
                      transport/TransportParams.cpp
                      transport/WaterTransport.cpp)

set(transport_includes ${include_cantera_dir}/transport/DustyGasTransport.h
                       ${include_cantera_dir}/transport/GasTransport.h
                       ${include_cantera_dir}/transport/HighPressureGasTransport.h
                       ${include_cantera_dir}/transport/LiquidTranInteraction.h
                       ${include_cantera_dir}/transport/LiquidTransport.h
                       ${include_cantera_dir}/transport/LiquidTransportData.h
                       ${include_cantera_dir}/transport/LiquidTransportParams.h
                       ${include_cantera_dir}/transport/LTPspecies.h
                       ${include_cantera_dir}/transport/MixTransport.h
                       ${include_cantera_dir}/transport/MultiTransport.h
                       ${include_cantera_dir}/transport/SimpleTransport.h
                       ${include_cantera_dir}/transport/SolidTransport.h
                       ${include_cantera_dir}/transport/SolidTransportData.h
                       ${include_cantera_dir}/transport/Tortuosity.h
                       ${include_cantera_dir}/transport/TransportBase.h
                       ${include_cantera_dir}/transport/TransportData.h
                       ${include_cantera_dir}/transport/TransportFactory.h
                       ${include_cantera_dir}/transport/TransportParams.h
                       ${include_cantera_dir}/transport/WaterTransport.h)

set(zerod_sources zeroD/ConstPressureReactor.cpp
                  zeroD/FlowDevice.cpp
                  zeroD/FlowReactor.cpp
                  zeroD/IdealGasConstPressureReactor.cpp
                  zeroD/IdealGasReactor.cpp
                  zeroD/Reactor.cpp
                  zeroD/ReactorBase.cpp
                  zeroD/ReactorFactory.cpp
                  zeroD/ReactorNet.cpp
                  zeroD/ReactorSurface.cpp
                  zeroD/Wall.cpp)

set(zerod_includes ${include_cantera_dir}/zeroD/ConstPressureReactor.h
                   ${include_cantera_dir}/zeroD/flowControllers.h
                   ${include_cantera_dir}/zeroD/FlowDevice.h
                   ${include_cantera_dir}/zeroD/FlowReactor.h
                   ${include_cantera_dir}/zeroD/IdealGasConstPressureReactor.h
                   ${include_cantera_dir}/zeroD/IdealGasReactor.h
                   ${include_cantera_dir}/zeroD/Reactor.h
                   ${include_cantera_dir}/zeroD/ReactorBase.h
                   ${include_cantera_dir}/zeroD/ReactorFactory.h
                   ${include_cantera_dir}/zeroD/ReactorNet.h
                   ${include_cantera_dir}/zeroD/ReactorSurface.h
                   ${include_cantera_dir}/zeroD/Reservoir.h
                   ${include_cantera_dir}/zeroD/Wall.h)

# Setup library
add_library(cantera STATIC ${root_includes}
                           ${base_sources}
                           ${base_includes}
                           ${clib_sources}
                           ${clib_includes}
                           ${cython_includes}
                           ${equil_sources}
                           ${equil_includes}
                           ${fortran_sources}
                           ${kinetics_sources}
                           ${kinetics_includes}
                           #${matlab_sources}
                           ${numerics_sources}
                           ${numerics_includes}
                           ${oned_sources}
                           ${oned_includes}
                           ${pch_sources}
                           ${thermo_sources}
                           ${thermo_includes}
                           ${tpx_sources}
                           ${tpx_includes}
                           ${transport_sources}
                           ${transport_includes}
                           ${zerod_sources}
                           ${zerod_includes})
target_include_directories(cantera PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(cantera PUBLIC
                           $<BUILD_INTERFACE:${include_dir}>
                           $<INSTALL_INTERFACE:include>)
target_include_directories(cantera PUBLIC
                           $<BUILD_INTERFACE:${Boost_INCLUDE_DIRS}>)
target_include_directories(cantera PUBLIC
                           $<BUILD_INTERFACE:${include_cantera_dir}/ext>)
target_link_libraries(cantera PRIVATE fmt libexecstream sundials_arkode_static sundials_cvodes_static sundials_ida_static sundials_kinsol_static sundials_nvecserial_static)

# Organization
source_group("include" FILES ${root_includes})
source_group("src\\base" FILES ${base_sources})
source_group("include\\base" FILES ${base_includes})
source_group("src\\clib" FILES ${clib_sources})
source_group("include\\clib" FILES ${clib_includes})
source_group("include\\cython" FILES ${cython_includes})
source_group("src\\equil" FILES ${equil_sources})
source_group("include\\equil" FILES ${equil_includes})
source_group("src\\fortran" FILES ${fortran_sources})
source_group("src\\kinetics" FILES ${kinetics_sources})
source_group("include\\kinetics" FILES ${kinetics_includes})
source_group("src\\matlab" FILES ${matlab_sources})
source_group("src\\numerics" FILES ${numerics_sources})
source_group("include\\numerics" FILES ${numerics_includes})
source_group("src\\oned" FILES ${oned_sources})
source_group("include\\oned" FILES ${oned_includes})
source_group("src\\pch" FILES ${pch_sources})
source_group("src\\thermo" FILES ${thermo_sources})
source_group("include\\thermo" FILES ${thermo_includes})
source_group("src\\tpx" FILES ${tpx_sources})
source_group("include\\tpx" FILES ${tpx_includes})
source_group("src\\transport" FILES ${transport_sources})
source_group("include\\transport" FILES ${transport_includes})
source_group("src\\zerod" FILES ${zerod_sources})
source_group("include\\zerod" FILES ${zerod_includes})

# Setup installation
install(TARGETS cantera
        EXPORT canteraTargets
        ARCHIVE DESTINATION lib)
install(EXPORT canteraTargets
        NAMESPACE ${NAMESPACE}
        DESTINATION ${CONFIG_INSTALL_DIR})
install(DIRECTORY ${include_cantera_dir}
        DESTINATION include
        FILES_MATCHING PATTERN *.h)
