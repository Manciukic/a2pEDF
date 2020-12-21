# Adaptive Partitioning EDF in the Linux Kernel
Final project for the course in [Advanced Kernel Programming @ Scuola Superiore 
Sant'Anna](https://retis.santannapisa.it/luca/AKP/).

## Description
This patch implements the a2pEDF scheduler (1) in place
of the previous gEDF.
a2pEDF's goal is to reduce the number of migrations of a
SCHED_DEADLINE task. To do so, it prevents pushes when
the current runqueue is not full and the target run queue is
chosen based on avalable bandwidth (instead of later deadline).
Pulls are allowed only by an empty runqueue and only from a
overloaded runqueue.

The patch has been tested on top of v5.9.8.

(1) Luca Abeni and Tommaso Cucinotta. 2020. Adaptive partitioning of real-time tasks on multiple processors. In Proceedings of the 35th Annual ACM Symposium on Applied Computing (SAC '20). Association for Computing Machinery, New York, NY, USA, 572–579. DOI:https://doi.org/10.1145/3341105.3373937

## License
a2pEDF implementation for the Linux Kernel
Copyright (C) 2020  Riccardo Mancini

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License along
with this program; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.
