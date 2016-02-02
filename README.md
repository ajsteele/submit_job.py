# submit_job.py
## Python script to streamline SGE job submission.

The script takes a small number of user-edited input variables:

* ``job_name = 'test_job'`` // Give your job an informative name, without spaces.
* ``memory_request = 1 # GB``
* ``runtime = 24 # hours``
* ``working_directory = '~'``
* ``output_base = '~/output'``
* ``use_gpu = False``  // If your job needs a GPU node, set this to true and relevant SGE commands will be added.

After these have been defined, the ``output_directory`` variable is created by combining ``job_name`` and a date-time string. This is created before the user's commands are specified because you might wish to use it to specify where a script puts its job-related output.

```
commands = """echo "Hello, world"
touch """ + output_directory + """test_file
sleep 10"""
```

Commands are then placed in the triple-quoted string, allowing multi-line input of several commands. As noted above, the ``output_directory`` variable is available if needed.
