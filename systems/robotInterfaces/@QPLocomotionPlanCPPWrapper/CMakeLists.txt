include_directories(..)

if (MATLAB_FOUND)
  if (LCM_FOUND)
    macro(add_qplocomotionplan_mex)
      add_mex(${ARGV} ${ARGV}.cpp)
      target_link_libraries(${ARGV} drakeQPLocomotionPlan drakeMexUtil)
    endmacro()

    add_qplocomotionplan_mex(getQPControllerInput) 
    add_qplocomotionplan_mex(start_time)
    add_qplocomotionplan_mex(setStartTime)
    add_qplocomotionplan_mex(getLastQPInput)
    add_qplocomotionplan_mex(isFinished)
    add_qplocomotionplan_mex(duration)

    add_subdirectory(private)
  endif()
endif()

