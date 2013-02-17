# Convenient NSTask executions

NMTask is a very simple subclass of NSTask that provides convenience
methods for executing a script and storing the response from that
script.

This is what you would want to use NSTask for in most cases, and so it
should be simpler.

## How it works

Using `- runScript:` you can run any shell script just as you would on
your command line.

    NMTask *task = [NMTask runScript:@"echo Hello > hello.txt"];

It is really just a convenience method for `- runTaskAtLaunchPath:withArguments:`:

    NMTask *task = [NMTask runTaskAtLaunchPath:@"/bin/sh" withArguments:@[@"-c", script]];

Responses and errors from executions are stored in `@response` and
`@errorMessage` respectively.

    NSLog(@"Response: %@", task.response);
    NSLog(@"Error: %@", self.error);

## License

Copyright (c) 2013 Nine Muses AB

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
