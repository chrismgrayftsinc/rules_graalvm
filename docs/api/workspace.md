<!-- Generated with Stardoc: http://skydoc.bazel.build -->

Bazel Workspace (non-Bzlmod) definitions.

<a id="rules_graalvm_repositories"></a>

## rules_graalvm_repositories

<pre>
rules_graalvm_repositories(<a href="#rules_graalvm_repositories-omit_rules_java">omit_rules_java</a>, <a href="#rules_graalvm_repositories-omit_bazel_skylib">omit_bazel_skylib</a>)
</pre>

Defines dependencies for the GraalVM Rules for Bazel.

This function only needs to be called if consuming the GraalVM Rules from a non-Bzlmod environment.
The only dependencies the rules have are: (1) `rules_java`, and (2) `bazel_skylib`. Either or both
can be omitted with the provided arguments.

**PARAMETERS**

| Name                                                                       | Description                                    | Default Value      |
| :------------------------------------------------------------------------- | :--------------------------------------------- | :----------------- |
| <a id="rules_graalvm_repositories-omit_rules_java"></a>omit_rules_java     | Omit the <code>rules_java</code> dependency.   | <code>False</code> |
| <a id="rules_graalvm_repositories-omit_bazel_skylib"></a>omit_bazel_skylib | Omit the <code>bazel_skylib</code> dependency. | <code>False</code> |