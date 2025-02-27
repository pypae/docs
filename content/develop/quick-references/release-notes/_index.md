---
title: Release notes
slug: /develop/quick-reference/release-notes
description: A changelog of highlights and fixes for each version of Streamlit.
keywords: changelog, release notes, version history
---

# Release notes

This page lists highlights, bug fixes, and known issues for the latest release of Streamlit. If you're looking for information about nightly releases or experimental features, see [Pre-release features](/develop/quick-reference/prerelease).

## Upgrade Streamlit

<Tip>

To upgrade to the latest version of Streamlit, run:

```bash
pip install --upgrade streamlit
```

</Tip>

## **Version 1.42.0 (latest)**

_Release date: February 4, 2025_

**Highlights**

- 👩‍💻 Introducing [`st.login()`](/develop/api-reference/user/st.login) and [`st.logout()`](/develop/api-reference/user/st.logout) to authenticate users with any OpenID Connect provider.

**Notable Changes**

- ❣️ [`st.table`](/develop/api-reference/data/st.table) supports Markdown ([#8785](https://github.com/streamlit/streamlit/issues/8785), [#10088](https://github.com/streamlit/streamlit/pull/10088)).
- ⏲️ [`st.spinner`](/develop/api-reference/status/st.spinner) can show elapsed time with `show_time=True` ([#6805](https://github.com/streamlit/streamlit/issues/6805), [#10072](https://github.com/streamlit/streamlit/pull/10072)).
- 💈 [`st.image`](/develop/api-reference/media/st.image) supports Markdown in the `caption` parameter ([#6808](https://github.com/streamlit/streamlit/issues/6808), [#10075](https://github.com/streamlit/streamlit/pull/10075)).
- ↕️ [`st.code`](/develop/api-reference/text/st.code) has a `height` parameter ([#7418](https://github.com/streamlit/streamlit/issues/7418), [#10080](https://github.com/streamlit/streamlit/pull/10080)).
- ↔️ Most charts default to using `use_container_width=True` ([#10064](https://github.com/streamlit/streamlit/pull/10064)).
- ❄️ [`SnowflakeConnection`](/develop/api-reference/connections/st.connections.snowflakeconnection) was updated to match the current Snowflake API, which changes its handling of keyword arguments in some cases ([#10122](https://github.com/streamlit/streamlit/pull/10122)).
- 🐁 Users can drag and drop dataframe columns to rearrange them ([#8796](https://github.com/streamlit/streamlit/issues/8796), [#10099](https://github.com/streamlit/streamlit/pull/10099)).

**Other Changes**

- 📌 Dataframes have column menus for users to sort and pin columns ([#10206](https://github.com/streamlit/streamlit/pull/10206)).
- 🚦 Dataframes support categorical indices ([#9647](https://github.com/streamlit/streamlit/issues/9647), [#10195](https://github.com/streamlit/streamlit/pull/10195)).
- 🛸 Dataframes show a hover highlight on rows ([#8096](https://github.com/streamlit/streamlit/issues/8096), [#10104](https://github.com/streamlit/streamlit/pull/10104)).
- ⚠️ When dataframes have cell values that are inconsistent with their configured type, Streamlit shows a tooltip describing the error ([#8253](https://github.com/streamlit/streamlit/issues/8253), [#9899](https://github.com/streamlit/streamlit/pull/9899)).
- ➰ If there is an existing asyncio event loop when a Streamlit app starts, the app will reuse it instead of creating a new one ([#10164](https://github.com/streamlit/streamlit/pull/10164)). Thanks, [DeltaGa](https://github.com/DeltaGa)!
- 🖼️ Streamlit recognizes `pyspark.sql.connect.dataframe.DataFrame` objects as dataframes ([#9953](https://github.com/streamlit/streamlit/issues/9953), [#9954](https://github.com/streamlit/streamlit/pull/9954)). Thanks, [OSalama](https://github.com/OSalama)!
- 😃 We've updated emoji validation for new emojis ([#10149](https://github.com/streamlit/streamlit/pull/10149)).
- 🔣 Material Symbols have been updated with the latest icons ([#10247](https://github.com/streamlit/streamlit/pull/10247)).
- 💅 Visual tweaks and improvements ([#8705](https://github.com/streamlit/streamlit/issues/8705), [#9823](https://github.com/streamlit/streamlit/pull/9823), [#10047](https://github.com/streamlit/streamlit/pull/10047), [#10048](https://github.com/streamlit/streamlit/pull/10048), [#10083](https://github.com/streamlit/streamlit/pull/10083), [#10087](https://github.com/streamlit/streamlit/pull/10087), [#10225](https://github.com/streamlit/streamlit/pull/10225)).
- ⭕ `st.image` displays rounded corners for consistent design ([#9999](https://github.com/streamlit/streamlit/pull/9999)).
- 🎩 Bug fix: Top margin is applied correctly in `st.columns` ([#10265](https://github.com/streamlit/streamlit/issues/10265), [#10268](https://github.com/streamlit/streamlit/pull/10268)).
- 💩 Bug fix: `react-syntax-highlighter` is aliased to prevent rendering errors in `st.code` ([#10231](https://github.com/streamlit/streamlit/issues/10231), [#10244](https://github.com/streamlit/streamlit/pull/10244)).
- 🧹 Bug fix: We improved error messages for `st.query_params` ([#10111](https://github.com/streamlit/streamlit/issues/10111), [#10237](https://github.com/streamlit/streamlit/pull/10237)).
- 🪱 Bug fix: Linting for `st.altair_chart` recognizes all Altair chart types ([#10202](https://github.com/streamlit/streamlit/pull/10202)).
- ↗️ Bug fix: `st.dataframe` supports raw Arrow data ([#5606](https://github.com/streamlit/streamlit/issues/5606), [#10191](https://github.com/streamlit/streamlit/pull/10191)).
- 🐍 Bug fix: `st.navigation` and `st.page_link` work when running in pure Python tests ([#10163](https://github.com/streamlit/streamlit/pull/10163)).
- ☠️ Bug fix: Retries were added to prevent a possible race condition when files are removed while Streamlit is running ([#10148](https://github.com/streamlit/streamlit/pull/10148)).
- 👽 Bug fix: When printing an app, `st.logo` will only print once ([#10165](https://github.com/streamlit/streamlit/issues/10165), [#10171](https://github.com/streamlit/streamlit/pull/10171)).
- 🌍 Bug fix: Material icons are marked to prevent translation ([#10168](https://github.com/streamlit/streamlit/issues/10168), [#10174](https://github.com/streamlit/streamlit/pull/10174)).
- 👻 Bug fix: `st.vega_lite_chart` correctly caches and updates its data ([#6689](https://github.com/streamlit/streamlit/issues/6689), [#10125](https://github.com/streamlit/streamlit/pull/10125)).
- 🦀 Bug fix: When a fragment ID is not found, Streamlit logs a warning but doesn't raise an error ([#9921](https://github.com/streamlit/streamlit/issues/9921), [#10130](https://github.com/streamlit/streamlit/pull/10130)).
- 🦋 Bug fix: The label on `st.expander` correctly fades when stale ([#10085](https://github.com/streamlit/streamlit/pull/10085)).
- 🦎 Bug fix: `st.date_input` provides better type hinting for its return value ([#9477](https://github.com/streamlit/streamlit/issues/9477), [#9620](https://github.com/streamlit/streamlit/pull/9620)). Thanks, [pranaybattu](https://github.com/pranaybattu)!
- 🐌 Bug fix: In dataframes, small float values display their first significant figure instead of displaying as 0 ([#10060](https://github.com/streamlit/streamlit/pull/10060)).
- 🕸️ Bug fix: When `rich` is installed, errors are only logged once. ([#10097](https://github.com/streamlit/streamlit/pull/10097)).
- 🦗 Bug fix: `st.text` preserves whitespace ([#10055](https://github.com/streamlit/streamlit/issues/10055), [#10062](https://github.com/streamlit/streamlit/pull/10062)).
- 🦂 Bug fix: Dataframe `width` is not ignored when `height` is changed ([#9762](https://github.com/streamlit/streamlit/issues/9762), [#10036](https://github.com/streamlit/streamlit/pull/10036)).
- 🦟 Bug fix: Multi index columns correctly handle empty labels ([#9749](https://github.com/streamlit/streamlit/issues/9749), [#10035](https://github.com/streamlit/streamlit/pull/10035)).
- 🦠 Bug fix: Pinned columns respect `column_order` in when configured in `st.dataframe` ([#9997](https://github.com/streamlit/streamlit/issues/9997), [#10034](https://github.com/streamlit/streamlit/pull/10034)).
- 🪰 Bug fix: Tooltips don't overflow to the left or right ([#9288](https://github.com/streamlit/streamlit/issues/9288), [#9452](https://github.com/streamlit/streamlit/issues/9452), [#9983](https://github.com/streamlit/streamlit/pull/9983)).
- 🪳 Bug fix: Disabled feedback widgets correctly show their value ([#10030](https://github.com/streamlit/streamlit/pull/10030)).
- 🕷️ Bug fix: Widgets correctly submit values if a user edits the value and immediately clicks a button ([#10007](https://github.com/streamlit/streamlit/issues/10007), [#10018](https://github.com/streamlit/streamlit/pull/10018)).
- 🐞 Bug fix: Some MIME types have been hardcoded to protect against browser misconfiguration ([#10004](https://github.com/streamlit/streamlit/issues/10004), [#10010](https://github.com/streamlit/streamlit/pull/10010)).
- 🐝 Bug fix: Files that unnecessarily inflated Streamlit's installation size were removed ([#10008](https://github.com/streamlit/streamlit/issues/10008), [#10011](https://github.com/streamlit/streamlit/pull/10011)).
- 🐜 Bug fix: `st.date_input` gives the correct type hint for the `value` parameter ([#10005](https://github.com/streamlit/streamlit/issues/10005), [#10006](https://github.com/streamlit/streamlit/pull/10006)).
- 🪲 Bug fix: `st.write` passes to `st.html` when `._repr_html()` is present for an object ([#9910](https://github.com/streamlit/streamlit/pull/9910)).
- 🐛 Bug fix: `st.html` preserves `target=_blank` if set in an HTML string ([#9972](https://github.com/streamlit/streamlit/issues/9972), [#9994](https://github.com/streamlit/streamlit/pull/9994)).

## Older versions of Streamlit

- [2024 release notes](/develop/quick-reference/release-notes/2024)
- [2023 release notes](/develop/quick-reference/release-notes/2023)
- [2022 release notes](/develop/quick-reference/release-notes/2022)
- [2021 release notes](/develop/quick-reference/release-notes/2021)
- [2020 release notes](/develop/quick-reference/release-notes/2020)
- [2019 release notes](/develop/quick-reference/release-notes/2019)
