# PhasicJ Agent Configuration Language

This package implements a simple Rust parser. This parser's language is used for
encoding PhasicJ Agent configuration information. (E.g., the `phasicj_exec`
option is used to point the agent to a PhasicJ executable with which it can
instrument JVM bytecode.)

The generated Rust source code for this parser is generated by the Pest parser
generator library from the grammar `:src/PjAgentConfLang.pest`.

Strings in this langauge are essentially comma-separated key-value pairs. For
example,

```
debug_dump_classes_before_instr=true,debug_dump_classes_after_instr=true
```

Helper code in this crate can interpret the parse tree and evaluate to an
easy-to-use `struct`, `PjAgentConf`.