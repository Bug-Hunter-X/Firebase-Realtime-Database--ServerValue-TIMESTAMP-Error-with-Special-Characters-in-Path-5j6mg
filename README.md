# Firebase Realtime Database: ServerValue.TIMESTAMP Error with Special Characters in Path

This repository demonstrates a bug in the Firebase Realtime Database where using `ServerValue.TIMESTAMP` with special characters (such as periods) in the database path results in a misleading error message.  The error message incorrectly suggests that `ServerValue.TIMESTAMP` is not a valid data type, when the actual problem is the path.  This repo provides a minimal reproducible example and a solution.

## Bug Reproduction

The `bug.js` file contains code that attempts to write a timestamp to a database path containing a period.  This will result in the error. 

## Solution

The `bugSolution.js` demonstrates a workaround.  The solution involves properly escaping special characters in the path or restructuring the database to avoid such characters in critical paths.