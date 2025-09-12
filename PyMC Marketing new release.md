# Release 0.16.0 · pymc-labs/pymc-marketing

# 0.16.0

![@juanitorduz](https://avatars.githubusercontent.com/u/22996444?s=40&v=4) [juanitorduz](/juanitorduz) released this 01 Sep 08:41

· [13 commits](/pymc-labs/pymc-marketing/compare/0.16.0...main) to main since this release

[0.16.0](/pymc-labs/pymc-marketing/tree/0.16.0)

[`2cb3168`](/pymc-labs/pymc-marketing/commit/2cb3168ff82af2a7c2290f41ad7df46ff03bfdd3)

This commit was created on GitHub.com and signed with GitHub’s **verified signature**.

GPG key ID: B5690EEEBB952194

Verified

[Learn about vigilant mode](https://docs.github.com/github/authenticating-to-github/displaying-verification-statuses-for-all-of-your-commits).

## What's Changed

### Major Changes 🛠

-   Handle release of pymc 5.25.0 by [@daniel-saunders-phil](https://github.com/daniel-saunders-phil) in [#1844](https://github.com/pymc-labs/pymc-marketing/pull/1844)
-   Migrate to prior module from pymc-extras by [@williambdean](https://github.com/williambdean) in [#1767](https://github.com/pymc-labs/pymc-marketing/pull/1767)

### New Features 🎉

-   Sensitivity analysis and marginal effects by [@drbenvincent](https://github.com/drbenvincent) in [#1673](https://github.com/pymc-labs/pymc-marketing/pull/1673)
-   Add `table` method to ModelBuilder to display rich table by [@williambdean](https://github.com/williambdean) in [#1786](https://github.com/pymc-labs/pymc-marketing/pull/1786)
-   Allow for indexing of apply parameters by [@williambdean](https://github.com/williambdean) in [#1847](https://github.com/pymc-labs/pymc-marketing/pull/1847)
-   index transformation variables in higher dimension cases by [@williambdean](https://github.com/williambdean) in [#1857](https://github.com/pymc-labs/pymc-marketing/pull/1857)
-   allow for arbitrary additive effects in MVITS model by [@williambdean](https://github.com/williambdean) in [#1861](https://github.com/pymc-labs/pymc-marketing/pull/1861)
-   Allow Lists and NumPy Arrays as Transformation Priors by [@timbo112711](https://github.com/timbo112711) in [#1879](https://github.com/pymc-labs/pymc-marketing/pull/1879)
-   Support HSGP instance for time\_varying\_media in MMM by [@cetagostini](https://github.com/cetagostini) in [#1881](https://github.com/pymc-labs/pymc-marketing/pull/1881)
-   Support HSGP instance for time\_varying\_intercept in MMM by [@cetagostini](https://github.com/cetagostini) in [#1894](https://github.com/pymc-labs/pymc-marketing/pull/1894)
-   Add Fivetran data loaders by [@cetagostini](https://github.com/cetagostini) in [#1887](https://github.com/pymc-labs/pymc-marketing/pull/1887)
-   Add more Basis implementations for use with EventEffect by [@TeemuSailynoja](https://github.com/TeemuSailynoja) in [#1911](https://github.com/pymc-labs/pymc-marketing/pull/1911)

### Bugfixes 🐛

-   hot fix (test match) by [@juanitorduz](https://github.com/juanitorduz) in [#1852](https://github.com/pymc-labs/pymc-marketing/pull/1852)
-   Update and reduce size multi\_mmm.nc by [@juanitorduz](https://github.com/juanitorduz) in [#1854](https://github.com/pymc-labs/pymc-marketing/pull/1854)
-   Deprecate and disable budget optimization method & Updating notebook by [@cetagostini](https://github.com/cetagostini) in [#1832](https://github.com/pymc-labs/pymc-marketing/pull/1832)
-   Handle 0-dim channel\_xr in create\_zero\_dataset by [@cetagostini](https://github.com/cetagostini) in [#1890](https://github.com/pymc-labs/pymc-marketing/pull/1890)
-   Fix grid shape logic in saturation\_curves and add tests by [@cetagostini](https://github.com/cetagostini) in [#1889](https://github.com/pymc-labs/pymc-marketing/pull/1889)
-   Updating prior predictive notebook by [@cetagostini](https://github.com/cetagostini) in [#1897](https://github.com/pymc-labs/pymc-marketing/pull/1897)
-   Streamlit Dependency Fix by [@timbo112711](https://github.com/timbo112711) in [#1904](https://github.com/pymc-labs/pymc-marketing/pull/1904)
-   Fix FourierEffect by [@PabloRoque](https://github.com/PabloRoque) in [#1909](https://github.com/pymc-labs/pymc-marketing/pull/1909)

### Documentation 📖

-   fix the link to Labs YouTube by [@williambdean](https://github.com/williambdean) in [#1822](https://github.com/pymc-labs/pymc-marketing/pull/1822)
-   Fix notebooks titles MMM in gallery by [@juanitorduz](https://github.com/juanitorduz) in [#1843](https://github.com/pymc-labs/pymc-marketing/pull/1843)
-   Remove reference to linear\_saturation function by [@williambdean](https://github.com/williambdean) in [#1833](https://github.com/pymc-labs/pymc-marketing/pull/1833)
-   Updating MMM Budget allocation examples, functionalities and dependencies by [@cetagostini](https://github.com/cetagostini) in [#1849](https://github.com/pymc-labs/pymc-marketing/pull/1849)
-   Add `rfm_train_test_split` example to CLV Quickstart by [@ColtAllen](https://github.com/ColtAllen) in [#1855](https://github.com/pymc-labs/pymc-marketing/pull/1855)
-   lift test requires 'date' in df\_lift\_test Data Frame with time\_varying\_media=True by [@timbo112711](https://github.com/timbo112711) in [#1818](https://github.com/pymc-labs/pymc-marketing/pull/1818)
-   MMM: Fix Scaling Intercept by [@juanitorduz](https://github.com/juanitorduz) in [#1845](https://github.com/pymc-labs/pymc-marketing/pull/1845)
-   Implement multidimensional scaling approach in regular MMM by [@cetagostini](https://github.com/cetagostini) in [#1862](https://github.com/pymc-labs/pymc-marketing/pull/1862)
-   Update MMM comparison table by [@williambdean](https://github.com/williambdean) in [#1878](https://github.com/pymc-labs/pymc-marketing/pull/1878)
-   Get marginal\_effects hdi estimates by [@PabloRoque](https://github.com/PabloRoque) in [#1885](https://github.com/pymc-labs/pymc-marketing/pull/1885)
-   Correcting typo around yml files and csv files. by [@cetagostini](https://github.com/cetagostini) in [#1888](https://github.com/pymc-labs/pymc-marketing/pull/1888)
-   Improve saturation function docs by [@daniel-saunders-phil](https://github.com/daniel-saunders-phil) in [#1892](https://github.com/pymc-labs/pymc-marketing/pull/1892)
-   Improvements on multidimensional notebook by [@daniel-saunders-phil](https://github.com/daniel-saunders-phil) in [#1876](https://github.com/pymc-labs/pymc-marketing/pull/1876)
-   Clean badges by [@juanitorduz](https://github.com/juanitorduz) in [#1896](https://github.com/pymc-labs/pymc-marketing/pull/1896)
-   Fourier transformation and HSGPs for streamlit app by [@timbo112711](https://github.com/timbo112711) in [#1898](https://github.com/pymc-labs/pymc-marketing/pull/1898)
-   Add usage examples and documentation to MMM modules by [@cetagostini](https://github.com/cetagostini) in [#1895](https://github.com/pymc-labs/pymc-marketing/pull/1895)
-   Assign coords to multidimensional fit\_data by [@PabloRoque](https://github.com/PabloRoque) in [#1902](https://github.com/pymc-labs/pymc-marketing/pull/1902)

### Maintenance 🔧

-   Add callback tracking to budget optimizer by [@cetagostini](https://github.com/cetagostini) in [#1829](https://github.com/pymc-labs/pymc-marketing/pull/1829)
-   Cosmetic changes to [#1829](https://github.com/pymc-labs/pymc-marketing/pull/1829) by [@PabloRoque](https://github.com/PabloRoque) in [#1830](https://github.com/pymc-labs/pymc-marketing/pull/1830)
-   Add support for time-based budget distribution in optimizer by [@cetagostini](https://github.com/cetagostini) in [#1841](https://github.com/pymc-labs/pymc-marketing/pull/1841)
-   fix(clv): Improve validation for missing columns in CLVModel by [@aaron1-z](https://github.com/aaron1-z) in [#1851](https://github.com/pymc-labs/pymc-marketing/pull/1851)
-   Adding arguments to model builder by [@cetagostini](https://github.com/cetagostini) in [#1867](https://github.com/pymc-labs/pymc-marketing/pull/1867)
-   Add causal graph support to MMM with DAG serialization by [@cetagostini](https://github.com/cetagostini) in [#1882](https://github.com/pymc-labs/pymc-marketing/pull/1882)
-   Refactor `ModelBuilder` into smaller classes by [@ColtAllen](https://github.com/ColtAllen) in [#1870](https://github.com/pymc-labs/pymc-marketing/pull/1870)
-   Update requirements.txt \[StreamlitApp\] by [@juanitorduz](https://github.com/juanitorduz) in [#1900](https://github.com/pymc-labs/pymc-marketing/pull/1900)
-   fix mypy overide by [@juanitorduz](https://github.com/juanitorduz) in [#1901](https://github.com/pymc-labs/pymc-marketing/pull/1901)
-   Updates Streamlit App Requirements by [@timbo112711](https://github.com/timbo112711) in [#1903](https://github.com/pymc-labs/pymc-marketing/pull/1903)
-   Multidimensional support in plot\_sensitivity\_analysis by [@PabloRoque](https://github.com/PabloRoque) in [#1886](https://github.com/pymc-labs/pymc-marketing/pull/1886)
-   Minor convenience to override model\_kwargs in build\_mmm\_from\_yaml by [@PabloRoque](https://github.com/PabloRoque) in [#1907](https://github.com/pymc-labs/pymc-marketing/pull/1907)
-   Normalize gaussian basis by [@PabloRoque](https://github.com/PabloRoque) in [#1912](https://github.com/pymc-labs/pymc-marketing/pull/1912)

## New Contributors

-   [@daniel-saunders-phil](https://github.com/daniel-saunders-phil) made their first contribution in [#1844](https://github.com/pymc-labs/pymc-marketing/pull/1844)
-   [@aaron1-z](https://github.com/aaron1-z) made their first contribution in [#1851](https://github.com/pymc-labs/pymc-marketing/pull/1851)

**Full Changelog**: [0.15.1...0.16.0](https://github.com/pymc-labs/pymc-marketing/compare/0.15.1...0.16.0)

### Contributors

-   [![@drbenvincent](https://avatars.githubusercontent.com/u/6765047?s=64&v=4)](https://github.com/drbenvincent)
-   [![@PabloRoque](https://avatars.githubusercontent.com/u/10153633?s=64&v=4)](https://github.com/PabloRoque)
-   [![@ColtAllen](https://avatars.githubusercontent.com/u/10178857?s=64&v=4)](https://github.com/ColtAllen)
-   [![@juanitorduz](https://avatars.githubusercontent.com/u/22996444?s=64&v=4)](https://github.com/juanitorduz)
-   [![@timbo112711](https://avatars.githubusercontent.com/u/25594987?s=64&v=4)](https://github.com/timbo112711)
-   [![@TeemuSailynoja](https://avatars.githubusercontent.com/u/33978952?s=64&v=4)](https://github.com/TeemuSailynoja)
-   [![@williambdean](https://avatars.githubusercontent.com/u/57733339?s=64&v=4)](https://github.com/williambdean)
-   [![@cetagostini](https://avatars.githubusercontent.com/u/59846724?s=64&v=4)](https://github.com/cetagostini)
-   [![@aaron1-z](https://avatars.githubusercontent.com/u/77638360?s=64&v=4)](https://github.com/aaron1-z)
-   [![@daniel-saunders-phil](https://avatars.githubusercontent.com/u/83777819?s=64&v=4)](https://github.com/daniel-saunders-phil)

drbenvincent, PabloRoque, and 8 other contributors

Assets 2

Loading

### Uh oh!

There was an error while loading. Please reload this page.

 -   👍
-   😄
-   🎉
-   ❤️
-   🚀
-   👀

 

🎉 1 williambdean reacted with hooray emoji

All reactions

-   🎉 1 reaction

1 person reacted