## CPU_timer

An object-oriented approach for timing program execution in modern Fortran (2008+).

## Usage:

```fortran

use, intrinsic :: iso_fortran_env, only: &
    WP     => REAL64, &
    IP     => INT32

use type_cpu_timer_mod, only: &
    cpu_timer_t

! Explicit typing only
implicit none

type (cpu_timer_t) :: timer
real (WP)          :: t
integer (IP)       :: units

!*Starting the timer

call timer%Start()

!* Stopping the timer

call timer%Stop()

!* Reading the time

t = timer%Get_elapsed_time( units ) ! Wall clock time
t = timer%Get_total_time( units )   ! Total processor time

!* units (optional) = 0 for seconds, or 1 for minutes, or 2 for hours

!* Get time stamp

call timer%Get_time_stamp()

```