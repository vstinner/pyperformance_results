+++++++++++++++++++
performance_results
+++++++++++++++++++

Results of the Python performance benchmark suite computed on the speed-python
server: compressed `perf JSON
<http://perf.readthedocs.io/en/latest/api.html#perf-json-format>`_ files.

Files are distributed under the MIT license (see ``COPYING`` file).

Website: https://github.com/haypo/performance_results

Results
=======

Directories
-----------

* ``2017-04-12-cpython``: CPython results computed since 2017-04-12. CPython
  2.7 is now configured with ``--enable-unicode=ucs4``, performance 0.5.5
  (dev).

* ``2017-03-31-cpython``: CPython results computed since 2017-03-31. CPython
  compiled with LTO and PGO. CPython now uses a Git repository.

  - ``2016-10-01_01-17-master-78a111c7d867.json.gz``: oldest file (start:
    2017-03-31), use performance 0.5.4 (dev) and perf 1.1 (dev)

* ``2016-12-28-cpython``: CPython results computed on the period
  2016-12-28..2017-02-10 (2 months). CPython compiled with LTO and PGO. CPython
  used a Mercurial repository.

  - ``2016-12-27_17-59-default-fa9933bf4ea0.json.gz``: oldest file (start:
    2016-12-28), use performance 0.5.0 and perf 0.9.0
  - ``2017-02-10_00-20-default-e91ec62da088.json.gz``: newest file (start:
    2017-02-10), use performance 0.5.1 and perf 0.9.3

Filename format
---------------

Example of filename: ``2016-01-01_10-25-default-0b8ff5216100.json.gz``

* ``2016-01-01``: date of the commit (year-month-day)
* ``10-25``: time of the commit with 24-hour format (hour-minute)
* ``default``: Git or Mercurial branch name
* ``0b8ff5216100``: commit identifier
* ``.json.gz``: File extension, JSON compressed by gzip

Use ``perf stats`` command to get the start/end dates when the benchmark was
run.


History
=======

* 2017-04-12: CPython 2.7 is now configured with ``--enable-unicode=ucs4``.
* 2017-03-31: old results removed, **new CPython results** to use Git commits
  instead of Mercurial.
* 2017-03-17: perf 1.0 released
* 2017-01: old results computed without PGO removed (unstable because of code
  placement), **new CPython results** using PGO
* 2016-12: speed-python server upgraded to Ubuntu 16.04
* 2016-11-04: old results computed with ``benchmarks`` removed, **new CPython
  results** (using LTO but not PGO) computed with the new ``performance``
  benchmark suite.
* 2016-08-24: performance 0.1 released
* 2016-06-02: perf 0.1 released
* 2016: speed.python.org uses the ``benchmarks`` benchmark suite
* 2008: ``benchmarks`` project created in December 2008 by Collin Winter and
  Jeffrey Yasskin for the Unladen Swallow project. The project was hosted at
  https://hg.python.org/benchmarks until Feb 2016


Software
========

* performance: http://pyperformance.readthedocs.io/
* perf: http://perf.readthedocs.io/


Hardware
========

Specification of the speed-python server used to run benchmarks.

* CPU:

  * 2 HP DL380 G7 Intel® Xeon® X5680 (3.33GHz/6-core/130W/12MB) FIO Processor Kit
  * 2 physical CPUs of 12 cores each: total: 24 cores
  * Intel(R) Xeon(R) CPU X5680 @ 3.33GHz,

* Memory: 4x 4GB (1x4GB) Dual Rank x4 PC3-10600 (DDR3-1333) Registered CAS-9 Memory Kit
* OS: Ubuntu 16.04.1 LTS
* Kernel: GNU/Linux 4.4.0-47-generic

Benchmarks are run on the NUMA node 1 (second CPU), Linux kernel options:

* ``isolcpus=1,3,5,7,9,11,13,15,17,19,21,23``
* ``rcu_nocbs=1,3,5,7,9,11,13,15,17,19,21,23``


Links
=====

Links:

* `speed.python.org <https://speed.python.org/>`_: CPython benchmark results
* `speed.pypy.org <http://speed.pypy.org/>`_: PyPy benchmark results
* `speed.pyston.org <http://speed.pyston.org/>`_: Pyston benchmark results

performance results:

* 2017-04-06: `[pyperformance] CPython results, 2017
  <http://pyperformance.readthedocs.io/cpython_results_2017.html>`_. CPython
  results and analyze of most significant optimizations and slowdowns.
* 2017-03-29: `speed.python.org results: March 2017
  <https://haypo.github.io/speed-python-org-march-2017.html>`_, screenshots of
  the most interesting benchmarks before removing CPython results using
  Mercurial commits.
* 2017-01-02: `[Speed] speed.python.org: recent issues to run benchmarks
  <https://mail.python.org/pipermail/speed/2017-January/000497.html>`_.
  Old results were removed, benchmarks now run with LTO+PGO on Ubuntu 16.04.
* 2016-11-04: `[Speed] New benchmarks results on speed.python.org
  <https://mail.python.org/pipermail/speed/2016-November/000471.html>`_.
  Benchmarks run on Ubuntu 14.04 with LTO but without PGO. Use NUMA node 1
  with CPU isolation, Turbo Boost disabled on the isolated CPUs, fixed
  CPU frequency (3.3 GHz). Results were lost (removed without backup).

