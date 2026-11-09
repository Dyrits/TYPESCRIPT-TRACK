# TypeScript Track

A repository for the dedicated [TypeScript track](https://exercism.org/tracks/typescript) on [Exercism](https://exercism.org/).

## About The Project

Exercises and solutions for the Exercism TypeScript track, kept together in one repository.

## License

No license file is present in this repository.

## Contact

Dyrits - https://github.com/Dyrits


## Test-tool dependency refresh (November 9, 2026)

Both existing exercise folders now use Node 26.13.0 LTS, Jest/Babel-Jest 29.7, TypeScript 6.0.3 and matching Jest/Node type packages. The original Exercism Babel/ESLint presets, exercise solutions, tests and learner metadata are unchanged. TypeScript uses bundler resolution for the existing Babel-transform test flow, with explicit Jest/Node ambient types as required by TypeScript 6. A first hello-world Yarn lock is added for repeatable installs; two-fer retains its Yarn lock workflow. Use Yarn Classic 1.22.22.

Run inside either `hello-world` or `two-fer`:

```sh
yarn install --frozen-lockfile
yarn test --coverage
yarn lint:ci
```

Baseline tests passed on Node 26: one hello-world test and three two-fer tests. Each candidate passed a fresh frozen install, typecheck, the same tests with 100% coverage of the tiny exercise solution, and ESLint. This is test-tool compatibility evidence for the two checked-in exercises, not a claim about other Exercism exercises.

The original two-fer audit has two low advisory IDs; the refreshed locks each have one existing low deepmerge ID, with no new IDs. The outdated jsdom/once dependency chain disappears with Jest 29. Deepmerge remains via Jest/ESLint configuration tooling and has no patched version in the audit. A newer Jest 30 candidate was rejected because it added glob/minimatch advisory IDs; no overrides or packages from that candidate are published. Jest 29 is a deliberate compatibility/security stop, not a claim to be the newest major. Yarn's own Node url.parse deprecation message remains.

References:
- https://jestjs.io/docs/29.7/upgrading-to-jest29
- https://devblogs.microsoft.com/typescript/announcing-typescript-6-0/
