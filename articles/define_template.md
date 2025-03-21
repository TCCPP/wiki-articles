# Where to put Template Definitions

A function or class template is itself not a function or class. Rather, a template is a description of what a function or class would look like. A concrete version (specialization) of a function or class can be generated (instantiated) from this description by substituting a given set of template arguments into the template.

The compiler will automatically generate the necessary instantiations as needed whenever you're using a template in your code. However, in order to instantiate a template, the compiler will generally need to know its definition. Thus, it is generally not possible to put the definition of templates into a separate .cpp source file and provide only declarations in a header.

