# XmasTasks
A virtual Christmas calendar in which you can solve tasks by opening one of the 24 doors

## Setup
1. You need to have node.js (20.9 or higher) installed on your machine.
2. Clone this repository.
3. Fill `runtimeConfig` in `nuxt.config.js` (see below).
4. Run `npm install` in the root directory of this repository.
5. Run `npm run build` in the root directory of this repository.
6. Run `npm start` in the root directory of this repository.
Your instance is now running on `localhost:3000`.

## `runtimeConfig`
| Key                    | Value                                                                                                                      |
|------------------------|----------------------------------------------------------------------------------------------------------------------------|
| `[key: number]`        | The task description for the i-th task                                                                                     |
| `start_unix_timestamp` | The unix timestamp for the start of the first task. <br/>Every next task will be unlocked exactly 24h after the last task. |
| `permutation`          | Array containing the number from 1 to 24 in any order                                                                      |

## Contributing
If you want to contribute to this project, feel free to do so. Just fork this repository and create a pull request with your changes.
