# Nightly Rust ICE

```text
$ rustc +nightly --version
rustc 1.78.0-nightly (6cc484351 2024-02-10)

$ cargo +nightly build
   Compiling crash-rustc v0.1.0 (C:\Users\jay\Desktop\crash-rustc)
thread 'rustc' panicked at compiler\rustc_metadata\src\creader.rs:195:32:
Failed to get crate data for crate15
stack backtrace:
   0:     0x7ff93f662972 - <std::sys_common::backtrace::_print::DisplayBacktrace as core::fmt::Display>::fmt::hc99197c9b2d6b3ef
   1:     0x7ff93f69563d - core::fmt::write::h2264ae2ff10f9d05
   2:     0x7ff93f658ff1 - <std::io::IoSliceMut as core::fmt::Debug>::fmt::h32e7988c01068207
   3:     0x7ff93f66279a - std::sys_common::backtrace::lock::h4ad46ad9c5ad405f
   4:     0x7ff93f665b59 - std::panicking::default_hook::h0ba92da552d0410c
   5:     0x7ff93f665815 - std::panicking::default_hook::h0ba92da552d0410c
   6:     0x7ff926429b15 - <tracing_subscriber[1a895b7d438f8c1d]::util::TryInitError as core[1a9ca60cf5f5707d]::fmt::Display>::fmt
   7:     0x7ff93f666163 - std::panicking::rust_panic_with_hook::haa5b2a955d6e9910
   8:     0x7ff93f666009 - <std::panicking::begin_panic_handler::StaticStrPayload as core::panic::PanicPayload>::take_box::h1fc7089d2c1f3293
   9:     0x7ff93f663279 - <std::sys_common::backtrace::_print::DisplayBacktrace as core::fmt::Display>::fmt::hc99197c9b2d6b3ef
  10:     0x7ff93f665cd6 - rust_begin_unwind
  11:     0x7ff93f6bb737 - core::panicking::panic_fmt::h3b76f05d3256bd9f
  12:     0x7ff92516a3db - <rustc_metadata[2f9ed4c92abfca28]::creader::CStore as rustc_session[3bf59b46651f552d]::cstore::CrateStore>::stable_crate_id
  13:     0x7ff9262656fd - <rustc_middle[9193cad70d79b3d1]::ty::visit::LateBoundRegionsCollector as rustc_type_ir[fbb395866ffc979a]::visit::TypeVisitor<rustc_middle[9193cad70d79b3d1]::ty::context::TyCtxt>>::visit_ty
  14:     0x7ff9252a6b00 - <rustc_middle[9193cad70d79b3d1]::query::on_disk_cache::OnDiskCache>::serialize
  15:     0x7ff9252d58a3 - <rustc_middle[9193cad70d79b3d1]::ty::context::TyCtxt>::serialize_query_result_cache
  16:     0x7ff925112dda - rustc_incremental[f90b8bd0ccf92d0f]::persist::save::save_work_product_index
  17:     0x7ff925116c73 - rustc_incremental[f90b8bd0ccf92d0f]::persist::save::save_work_product_index
  18:     0x7ff92510ff77 - rustc_incremental[f90b8bd0ccf92d0f]::persist::load::setup_dep_graph
  19:     0x7ff925119c52 - rustc_incremental[f90b8bd0ccf92d0f]::persist::save::save_work_product_index
  20:     0x7ff9251105b0 - rustc_incremental[f90b8bd0ccf92d0f]::persist::load::setup_dep_graph
  21:     0x7ff925119e0b - rustc_incremental[f90b8bd0ccf92d0f]::persist::save::save_work_product_index
  22:     0x7ff92511175f - rustc_incremental[f90b8bd0ccf92d0f]::persist::save::save_dep_graph
  23:     0x7ff9224601de - rustc_driver_impl[b32f8017ee93a888]::main
  24:     0x7ff9224699d1 - rustc_driver_impl[b32f8017ee93a888]::main
  25:     0x7ff92245c48d - rustc_driver_impl[b32f8017ee93a888]::main
  26:     0x7ff92245def8 - rustc_driver_impl[b32f8017ee93a888]::main
  27:     0x7ff92249b74f - rustc_driver_impl[b32f8017ee93a888]::main
  28:     0x7ff92249a678 - rustc_driver_impl[b32f8017ee93a888]::main
  29:     0x7ff93f676b1c - std::sys::pal::windows::thread::Thread::new::h12285e0320d9cc9c
  30:     0x7ff9d256257d - BaseThreadInitThunk
  31:     0x7ff9d420aa58 - RtlUserThreadStart

error: the compiler unexpectedly panicked. this is a bug.

note: we would appreciate a bug report: https://github.com/rust-lang/rust/issues/new?labels=C-bug%2C+I-ICE%2C+T-compiler&template=ice.md

note: please attach the file at `C:\Users\jay\Desktop\crash-rustc\rustc-ice-2024-02-11T02_19_09-221228.txt` to your bug report

note: compiler flags: --crate-type proc-macro -C prefer-dynamic -C embed-bitcode=no -C debuginfo=2 -C incremental=[REDACTED]

note: some of the compiler flags provided by cargo are hidden

query stack during panic:
end of query stack
error: could not compile `crash-rustc` (lib)
```
