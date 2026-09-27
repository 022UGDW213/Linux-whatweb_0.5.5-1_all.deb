# whatweb 0.5.5-1 (`all`) — unpacked Debian/Ubuntu package

This repository is a **drop of a third-party Debian package**, not original software.
It contains the Debian package `whatweb 0.5.5-1` from the Debian *bullseye* release,
shipped as a ZIP of the package's `ar` members, plus a web-page capture that records
where the copy came from.

Nothing in this repository was written by the repository owner. WhatWeb itself is
upstream software by Andrew Horton and Brendan Coles, licensed GPL-2.0+; the Debian
packaging is by Laszlo Boszormenyi (GCS) `<gcs@debian.org>`. See [Licence](#10-licence).

Every number below was produced by a command run on this workstation, and the command is
shown next to it. §11 records both the 2026-09-26 measurement pass and a 2026-09-27
re-verification pass that re-ran the same commands; where the two disagree, the corrected
value is the one in the section body. Values that could **not** be verified are marked as
such instead of being estimated.

---

## 1. What WhatWeb actually is

WhatWeb is a real, long-standing **web-technology fingerprinting scanner** written in
Ruby. It identifies what a website is running — content management systems, blogging
platforms, analytics/statistic packages, JavaScript libraries, web servers, embedded
devices — plus version numbers, e-mail addresses, account IDs, web framework modules
and SQL errors. It has an "aggression level" that trades stealth against thoroughness
(the default, `stealthy`, makes a single HTTP request).

- Upstream source: <https://github.com/urbanadventurer/WhatWeb> — verified present in
  the package's own copyright file: `Source: https://github.com/urbanadventurer/WhatWeb`
  (`data/usr/share/doc/whatweb/copyright`).
- Authors: Andrew Horton ([urbanadventurer](https://github.com/urbanadventurer/)) and
  Brendan Coles ([bcoles](https://github.com/bcoles/)) — from the bundled
  `usr/share/doc/whatweb/README.md.gz` and the header of `usr/bin/whatweb`.
- Upstream homepage: <https://www.morningstarsecurity.com/research/whatweb>
  (`Homepage:` field of the package `control` file).

Version context (checked live on 2026-09-26, re-checked 2026-09-27): the **upstream
project has moved on** —
`https://raw.githubusercontent.com/urbanadventurer/WhatWeb/master/README.md` states
"Latest Release: v0.6.4. April 3, 2026". The copy in this repository is the older
**0.5.5** (upstream changelog, `usr/share/doc/whatweb/changelog.gz`: "Version 0.5.5 -
January 16, 2021"; the Debian package `0.5.5-1` was built 2021-01-15 — `changelog.Debian.gz`
entry dated `Fri, 15 Jan 2021 20:47:34 +0100`, matching the mirror's
`Last-Modified: Fri, 15 Jan 2021 21:42:47 GMT` in §3).

---

## 2. Exact repository contents

`git ls-tree -r --long HEAD` at the pre-existing tip `f12719e` showed exactly **4 tracked
files**, with no others — and specifically **no `LICENSE`** and **no `.gitignore`**; see §7.
(`README.md`, this file, is added by the 2026-09-26 commit and is the fifth tracked file.)

| Path | Bytes | sha256 |
|---|---:|---|
| `whatweb_0.5.5-1_all.zip` | 2,307,537 | `46846a63c03193faf5a38ec9458c590088dae37b3e6a0068324ab4d8ec6aa776` |
| `Web capture_23-10-2022_52453_ubuntu.pkgs.org.jpeg` | 281,860 | `e31b18acd7ff05a14788ec7cce849a49bd7ae4c9a987d7f3b51c6a4101ba79a1` |
| `src/Next generation web scanner.md` | 4,878 | `b0199ebc003a8978b0514246de66315c16e933a4115cfbfab864b38a07ff8b9b` (as of 2026-09-26; was 3,737 bytes / `219c59d010bfebbabccc1a75dcd7269cdbed92742d469b92f15432d76d88fea9` before the correction header in §6) |
| `.src/jpeg` | 316 | `2549cbe4f422a0994564bb04bd02e1f4591e8785a77c68de0f27c3aacc2dad50` |

Command:
```sh
sha256sum whatweb_0.5.5-1_all.zip \
  "Web capture_23-10-2022_52453_ubuntu.pkgs.org.jpeg" \
  "src/Next generation web scanner.md" .src/jpeg
ls -l whatweb_0.5.5-1_all.zip "Web capture_23-10-2022_52453_ubuntu.pkgs.org.jpeg" \
  "src/Next generation web scanner.md" .src/jpeg
```

**Note on the repository name.** The repository is called `Linux-whatweb_0.5.5-1_all.deb`,
but it does **not** contain a `.deb` file. It contains a ZIP whose members are the
`ar` members of that `.deb`. §3 shows how to rebuild the `.deb`.

---

## 3. What is inside the ZIP, and proof of where it came from

`unzip -l whatweb_0.5.5-1_all.zip`:

```
  Length      Date    Time    Name
        0  2022-10-23 11:34   whatweb_0.5.5-1_all/
        4  2021-01-15 23:47   whatweb_0.5.5-1_all/debian-binary
    48060  2021-01-15 23:47   whatweb_0.5.5-1_all/control.tar.xz
  2257900  2021-01-15 23:47   whatweb_0.5.5-1_all/data.tar.xz
---------                     -------
  2305964                     4 files
```

That is exactly the three members of a `ar`-format Debian binary package
(`debian-binary` + `control.tar.xz` + `data.tar.xz`), unzipped.

**Provenance verified against the live Debian mirror** (2026-09-26):

1. The mirror file is live and unchanged since 2021:
   ```sh
   curl -sI http://ftp.de.debian.org/debian/pool/main/w/whatweb/whatweb_0.5.5-1_all.deb
   ```
   → `HTTP/1.1 200 OK`, `Content-Length: 2306152`,
   `Last-Modified: Fri, 15 Jan 2021 21:42:47 GMT`
   (`https://deb.debian.org/debian/pool/main/w/whatweb/whatweb_0.5.5-1_all.deb` → `HTTP/2 200`, same size).
2. Its three `ar` members hash **identically** to the members inside this repo's ZIP:

| Member | sha256 (ZIP member = live Debian `.deb` member) |
|---|---|
| `debian-binary` | `d526eb4e878a23ef26ae190031b4efd2d58ed66789ac049ea3dbaf74c9df7402` |
| `control.tar.xz` | `bff79925faf4864b0c67039a0ae92b25a350437ad1d4b3c4cae64b8d174623e8` |
| `data.tar.xz` | `3741de8c7c7d3fc77b26c61b9d712264563b778e80e7d23482bdfd4cf1ebdc73` |

   Command: `ar x whatweb_real.deb && sha256sum debian-binary control.tar.xz data.tar.xz`
   compared with `sha256sum whatweb_0.5.5-1_all/{debian-binary,control.tar.xz,data.tar.xz}`.

3. Rebuilding an `ar` archive from the ZIP's three members, reusing the header fields
   read out of the live Debian `.deb`, produces a file **byte-identical** to that
   `.deb`:
   - live mirror `.deb` size 2,306,152 bytes
   - sha256 `9a9e233d4a5340e9899b44aada049a5212bfae90a98ad7525b7d109f150afd78`
   - rebuild comparison: `BYTE-IDENTICAL: True`

So the ZIP in this repository is a repackaging of the unmodified Debian *bullseye*
`whatweb_0.5.5-1_all.deb`, and that file is still served today.

To rebuild the `.deb` from the ZIP yourself (on a box with GNU `ar`):
```sh
unzip -q whatweb_0.5.5-1_all.zip && cd whatweb_0.5.5-1_all
ar rc ../whatweb_0.5.5-1_all.deb debian-binary control.tar.xz data.tar.xz
```
*Measured caveat:* GNU `ar` writes its own header metadata, so a plain `ar rc` rebuild
has the same size (2,306,152 B) and the same three payloads but is **not** byte-identical
to the Debian file. `cmp` reports the first difference at byte 22, inside the first
member header. A byte-level comparison of the two headers shows every difference is
header metadata only:

| Offset | Live Debian `.deb` (written by `dpkg-deb`) | `ar rc` rebuild |
|---|---|---|
| 21 | space (name padded: `debian-binary   `) | `/` (GNU `ar` appends a slash: `debian-binary/`) |
| 24-35 (`mtime`) | `1610740054` (2021-01-15) | `0` |
| 48-55 (`mode`) | `100644` | `644` |

Reusing the original headers reproduces the Debian file exactly, as shown above.

Package page cross-check: `https://packages.debian.org/bullseye/whatweb` returns
`<title>Debian -- Details of package whatweb in bullseye</title>` and
`Package: whatweb (0.5.5-1)`.

---

## 4. Package metadata — read out of `control.tar.xz`

`tar -xJf control.tar.xz -C ctl && cat ctl/control`:

| Field | Value |
|---|---|
| `Package` | `whatweb` |
| `Version` | `0.5.5-1` |
| `Architecture` | `all` |
| `Maintainer` | `Laszlo Boszormenyi (GCS) <gcs@debian.org>` |
| `Installed-Size` | `19039` (KB) |
| `Depends` | `ruby (>= 1:2.4) \| ruby-interpreter, ruby-ipaddress, ruby-addressable` |
| `Recommends` | `ruby-json, ruby-rchardet` |
| `Section` / `Priority` | `web` / `optional` |
| `Homepage` | `https://www.morningstarsecurity.com/research/whatweb` |
| `Ruby-Versions` | `all` |
| `Description` | `Next generation web scanner` (full text in §6) |

`control.tar.xz` also carries `md5sums` (1,861 entries), `preinst`, `postinst`,
`prerm`, `postrm` (debhelper 13.3.1–generated). The `postinst` performs one
`dpkg-maintscript-helper symlink_to_dir /usr/share/whatweb/my-plugins
/var/lib/whatweb/my-plugins 0.4.9-2`.

---

## 5. Package contents — measured, not copied

`tar -xJf data.tar.xz -C data && find data -type f | wc -l`:

| Measurement | Value |
|---|---:|
| Files in `data.tar.xz` | **1,861** (identical to the `md5sums` line count) |
| Directories in `data.tar.xz` | 16 |
| Unpacked size (sum of the 1,861 file bytes) | **18,531,007** bytes (17.67 MiB) |
| `data/usr/bin/whatweb` | 1 executable script |
| `data/usr/lib/ruby/vendor_ruby/` | 27 files (core scanner + `whatweb/` submodules) |
| `data/usr/share/` | 1,833 files |
| `data/usr/share/whatweb/plugins/` | **1,821 files** = 1,818 `.rb` plugin definitions + `IpToCountry.csv`, `country-ips.dat`, `country-codes.txt` |
| `data/usr/share/whatweb/my-plugins/` | 7 files, `plugin-tutorial-1.rb` … `plugin-tutorial-7.rb` |

The seven `my-plugins/plugin-tutorial-*.rb` files are **upstream WhatWeb's own shipped
tutorials**, not this repository's or its owner's work. Each carries WhatWeb's placeholder
author/website lines verbatim — `"Your preferred name <email@address>"`,
`website "http://example.com/"`, and in tutorial 3 `"@examplename"` — exactly as published
in the Debian package:

```sh
grep -c 'preferred name\|example\.com' data/usr/share/whatweb/my-plugins/*.rb
# → 2 lines per file, except plugin-tutorial-7.rb → 4  (all 7 files match)
```

They are correctly attributed third-party content (§10), not this repository's data and not
a measurement: the placeholder strings are upstream's, so they are left byte-for-byte.

The unpacked-size figure is the sum of the extracted files' bytes:

```sh
find data -type f -printf '%s\n' | awk '{s+=$1} END {print s}'
# → 18531007
tar -tvJf data.tar.xz | awk '$1 !~ /^d/ {s+=$3; n++} END {print n, s}'
# → 1861 18531007
```

`du -sb data` reports **18,662,079** for the same tree, because it also counts the 16
directory entries (all 4 KiB except `plugins/` at 68 KiB — 131,072 bytes in total;
`find . -type d -printf '%s\n' | awk '{s+=$1} END {print s}'` → `131072`). The 18,662,079
figure is therefore a `du` total, **not** a sum of file bytes, and is not used as the
package's unpacked size here. dpkg's own `Installed-Size: 19039` (KB) in §4 is a third,
independent estimate (dpkg's block-accounting estimate, 18.59 MiB).

### Plugin count, resolved exactly

There are 1,825 `.rb` plugin files in total (1,818 + 7), but the loader registers
**1,824** unique plugin names, because one name is defined twice:
`nopCommerce` appears in both `plugins/nop-commerce.rb` and `plugins/nopcommerce.rb`
(the plugin registry is a hash keyed by name, so the duplicate collapses).

Verified three ways, all agreeing (all three re-run on 2026-09-27):

- `ruby <scratch>/bin/whatweb --list-plugins | grep '^Total'` → `Total: 1824 Plugins`
- a direct call to the loader: `PluginSupport.load_plugins; Plugin.registered_plugins.size` → `registered_total=1824`, of which `tutorial_plugins=7`
- name extraction from the shipped files (`^\s*name\s+'…'` — note `plugins/safedog.rb` uses single quotes): `total names: 1825  unique: 1824  dups: {'nopCommerce': 2}`

(`<scratch>` is the extraction layout defined in §9; `whatweb-cli` — the name used in the
first pass of this README — **does not exist in the package**. The only executable shipped
is `usr/bin/whatweb`.)

The package's own bundled `usr/share/doc/whatweb/README.md.gz` carries the badge
`plugins-1824`, matching this measurement.

---

## 6. Honest note: the copied page capture contradicts the package in three places

`src/Next generation web scanner.md` is a **verbatim copy of a pkgs.org-style package
page** (its own body ends with `©2009-2022 - Packages for Linux and Unix`). It is kept
as a provenance artifact. Three of its statements do **not** match the package bytes it
sits next to, and the measured value is given here instead:

| Statement in the copied page | What I measured |
|---|---|
| `Files 8` (the page's own file list immediately below it names **10** paths) | the package installs **1,861** files (`find data -type f \| wc -l`); the page's list is a truncated page widget, not a package fact |
| `Repository  Debian Main arm64 Official` | this package is `Architecture: all` (`control` field), and its members are byte-identical to the architecture-independent file served from Debian's pool at `pool/main/w/whatweb/whatweb_0.5.5-1_all.deb` — verified in §3 |
| `Changelog 10 / [2022-10-23 - Juan JSP] {<22ugdw21@gmail.com>}` | the package's real changelog (`usr/share/doc/whatweb/changelog.Debian.gz`) is by `Laszlo Boszormenyi (GCS) <gcs@debian.org>`, latest entry `whatweb (0.5.5-1) unstable; urgency=medium … Fri, 15 Jan 2021 20:47:34 +0100`. The `2022-10-23 - Juan JSP` line is a **capture-time annotation on the web page**, not a real changelog entry |

One statement in the copied page *is* real: it quotes the package's `Description`
verbatim — "WhatWeb has over 900 plugins". That text is still literally what the
`control` file says (`grep 'over 900 plugins' ctl/control`), even though the true
current count is 1,824; it is an upstream wording, not a measurement.

A dated correction header was prepended to `src/Next generation web scanner.md` on
2026-09-26 pointing at this section; the captured page text below the header is
unaltered, and the file's pre- and post-header hashes are recorded in §2.

Two precision notes on that file's shape, both measured on 2026-09-27:

- The captured **page** text ends with `©2009-2022 - Packages for Linux and Unix`
  (confirmed independently by OCR of the screenshot, §8). Below that line the markdown
  file carries two further lines that are **not** page content — an owner-appended
  `.src/` pointer and the GitHub blob URL of the screenshot:
  `tail -2 "src/Next generation web scanner.md"`.
- The header's claim that the text below it is unaltered is exact:
  `git show f12719e:"src/Next generation web scanner.md" > /tmp/pre.md` then
  `tail -n +4 "src/Next generation web scanner.md" > /tmp/post.md` gives an **empty**
  `diff` (the header is exactly the three prepended `>` lines).

---

## 7. The `.src/jpeg` file is not a JPEG

`.src/jpeg` is a 316-byte **ASCII text** file — `file .src/jpeg` → `ASCII text` — and it
contains no JPEG data. It is a **mangled descendant of** the repository's original
`.gitignore`, not that file as committed: five later commits on 2022-10-23 rewrote it.
(The first pass of this README described it as the original `.gitignore` with "three extra
lines appended". That is wrong on both counts and is corrected here.)

The original `.gitignore` was 13 lines / 75 bytes (`git show fd58e04:.gitignore | wc -lc`).
At the rename commit `23be4fc` the file was that list plus exactly **one** appended URL
line (14 lines / 234 bytes). Today it is 24 lines / 316 bytes and no longer equals the
original — `diff` replaces every line:

```sh
git show fd58e04:.gitignore > /tmp/orig_gitignore && diff -u /tmp/orig_gitignore .src/jpeg
# → *.tar and *.tar.* are reduced to " *." and "*.", *.log.* / pkg/ / src/ are gone,
#   every surviving glob gained a leading space, and 14 lines were added
for c in 23be4fc 9f52163 02b3f8d daae854 15b62e5 f12719e; do git show $c:.src/jpeg | wc -lc; done
# → 14 234 | 16 269 | 16 161 | 17 275 | 24 314 | 24 316
```

| Commit (all 2022-10-23) | Subject | `.src/jpeg` |
|---|---|---:|
| `23be4fc` | `Rename .deb to .src/jpeg` | 14 lines / 234 B (original `.gitignore` + 1 URL line) |
| `9f52163` | `i` | 16 lines / 269 B |
| `02b3f8d` | `i` | 16 lines / 161 B |
| `daae854` | `i` | 17 lines / 275 B |
| `15b62e5` | `.src/` | 24 lines / 314 B |
| `f12719e` | `.src` | 24 lines / **316 B** (current) |

What survives is an ignore-glob list — now `*.`, `*.jar`, `*.exe`, `*.msi`, `*.zip`,
`*.tgz`, `*.log`, `*.sig`, `*.pkg`, `*.jpeg`, `*.https`, `*.` (`nl -ba .src/jpeg`) — inside
owner-authored structural lines. The file still names `whatweb_0.5.5-1_all.zip` and links
the screenshot inside this repository, so the first pass's *substance* about the pointers
holds; only its account of the file's provenance and the "three extra lines" was wrong.

Git history shows the rename chain, so the repo currently has **no active `.gitignore`**
and two files that the original ignore rules targeted (`*.zip`, `*.jpeg`) are tracked:

```
6939bc0  Rename .gitignore to .src
1ae9f25  Rename .src to .deb
23be4fc  Rename .deb to .src/jpeg
```
(`git log --follow --name-status -- .src/jpeg`)

---

## 8. The screenshot

`Web capture_23-10-2022_52453_ubuntu.pkgs.org.jpeg` — `file` reports
`JPEG image data, JFIF standard 1.01, baseline, precision 8, 1484x1723, components 3`,
281,860 bytes.

Its **filename** is the only record of where this copy was taken from: a web capture of
`ubuntu.pkgs.org` dated 2022-10-23. The repository's own last commit is
`f12719e956c7c38020c9fcf68607c4b1baa9ddae`, committed `2022-10-23T06:33:30-04:00`
(= `2022-10-23T10:33:30Z`; `git log -1 --format='%H%n%cI'`), i.e. the same day.
Tesseract OCR of the image returns a pkgs.org-style repository sidebar, and its matches
are repeatable (re-run 2026-09-27):

```sh
tesseract "Web capture_23-10-2022_52453_ubuntu.pkgs.org.jpeg" stdout > /tmp/ocr_full.txt
wc -c < /tmp/ocr_full.txt   # → 1217 characters of OCR text
for s in "Ubuntu Repositories" "Ubuntu Main" "Ubuntu Universe" "Ubuntu Updates" amd64 arm64 \
         whatweb "0.5.5"; do printf '%-24s -> %s\n' "$s" "$(grep -c -i -- "$s" /tmp/ocr_full.txt)"; done
# → Ubuntu Repositories    -> 1
#    Ubuntu Main           -> 1
#    Ubuntu Universe       -> 1
#    Ubuntu Updates        -> 4
#    amd64                 -> 32
#    arm64                 -> 22
#    whatweb               -> 0
#    0.5.5                 -> 0
```

So the image really is a repository/sidebar capture: it contains the sidebar names the
first pass cited, and it does **not** contain the package name or version. That makes the
image consistent with a pkgs.org page, but a screenshot cannot prove package bytes — so
the bytes are proved against the live Debian mirror in §3 instead. The OCR is lossy
(decorated numerals come out as noise), so it is used only for this consistency check.

---

## 9. Does the shipped code actually run? Yes — measured here

The packaged scanner was extracted and executed on this workstation with the local
Ruby (`ruby 3.0.2p107 (2021-07-07 revision 0db68f0233) [x86_64-linux-gnu]`), with no
files installed system-wide — re-measured 2026-09-27.

**There is no `whatweb-cli` in this package.** The only executable it ships is
`usr/bin/whatweb` (`find data -type f -perm -u+x` → `./usr/bin/whatweb`, and nothing
else). The first pass of this README cited `ruby <extracted>/ruby/whatweb-cli`, a path
that does not exist; the commands below are the ones that actually run.

WhatWeb's loader (`usr/lib/ruby/vendor_ruby/whatweb.rb`) looks for its plugins next to the
library (`<libs>/../plugins`, then `/usr/share/whatweb`), so the extraction needs one
specific layout: library files in `ruby/`, and `plugins/` + `my-plugins/` one level up.

```sh
# 1. unpack the ZIP's ar members, then the members themselves
unzip -q whatweb_0.5.5-1_all.zip && cd whatweb_0.5.5-1_all
mkdir ctl data && tar -xJf control.tar.xz -C ctl && tar -xJf data.tar.xz -C data

# 2. scratch layout:  /tmp/wws/ruby/<libs>  +  /tmp/wws/plugins , /tmp/wws/my-plugins
mkdir -p /tmp/wws/bin /tmp/wws/ruby
cp -r data/usr/share/whatweb/plugins data/usr/share/whatweb/my-plugins /tmp/wws/
cp -r data/usr/lib/ruby/vendor_ruby/* /tmp/wws/ruby/
cp data/usr/bin/whatweb /tmp/wws/bin/

# 3. run it
export RUBYLIB=/tmp/wws/ruby
ruby /tmp/wws/bin/whatweb --version
# → WhatWeb version 0.5.5 ( https://www.morningstarsecurity.com/research/whatweb/ )

ruby /tmp/wws/bin/whatweb --list-plugins | grep '^Total'
# → Total: 1824 Plugins
```

### The live scan — re-measured 2026-09-27

The colour option is `--colour=never`; `--no-colour` is rejected by this build.

The two iBot-stack services the first pass scanned (`127.0.0.1:3000`, `127.0.0.1:18789`)
were **not running** on 2026-09-27, so those outputs could not be re-produced. The scan
below targets a service that *was* up, and the port probe is included so the claim is
checkable:

```sh
ruby /tmp/wws/bin/whatweb --no-errors --colour=never http://127.0.0.1:18900/health
# → http://127.0.0.1:18900/health [200 OK] Country[RESERVED][ZZ], IP[127.0.0.1]

ruby /tmp/wws/bin/whatweb --no-errors --colour=never http://127.0.0.1:18900/
# → http://127.0.0.1:18900/ [401 Unauthorized] Country[RESERVED][ZZ], IP[127.0.0.1]

for p in 3000 18789 9008 9009 9003 9002 18900 18901 4002 4003 4040 9007 18790; do
  printf '%s ' "$p"; curl -s -m 3 -o /dev/null -w '%{http_code}\n' "http://127.0.0.1:$p/health"
done
# → only 18900 answered 200; every other port answered 000 (connection refused)
```

That is a real fingerprint rather than a bare 200: Mythos Cortex on `:18900` serves
`/health` unauthenticated and requires its `X-API-Token` header on every other endpoint
(per the V8 repo's `AGENTS.md`), and the scanner reports exactly that split — 200 on
`/health`, 401 on `/`.

**Dated 2026-09-26 measurements, NOT reproducible on 2026-09-27** (kept as dated history
because the services were down on the re-verification date; treat them as unverified
today, not as current fact):

- `http://127.0.0.1:3000 [302 Found] Cookies[ibot_loggedout,ibot_session],
  RedirectLocation[/Dashboard], X-Frame-Options[SAMEORIGIN]` and
  `http://127.0.0.1:3000/portal [200 OK] HTML5` — the iBot UI.
- `http://127.0.0.1:18789/health [200 OK] X-Powered-By[Express]` — the iBot gateway.

So the package in this repository is not a dead archive: the shipped 0.5.5 code runs and
fingerprints live services. The scanner needs Ruby plus `ruby-ipaddress` /
`ruby-addressable`; both are installed here (`gem list` → `addressable (2.9.0)`,
`ipaddress (0.8.3)`), which is why the runs above work. `ruby-rchardet`, an upstream
*Recommends*, is **not** installed.

**Not verified here:** no `.deb` was installed on this machine (`dpkg -i` was not run;
the package was only extracted and executed in place), so installation/dependency
resolution behaviour is unverified. There is also no Ubuntu build of this package in
this repository — the copy is the Debian *bullseye* build.

---

## 10. Licence

This is **not** the repository owner's work, and there is **no licence file of its own**
in this repository (at commit `f12719e` `git ls-tree -r HEAD` listed 4 files, none of
them `LICENSE`). The package carries its own upstream licence:

- WhatWeb: **GPL-2.0-or-later**. From the bundled
  `usr/share/doc/whatweb/copyright` (Debian machine-readable format 1.0):
  `Upstream-Name: WhatWeb`, `Source: https://github.com/urbanadventurer/WhatWeb`,
  `Copyright: 2009-2019 Andrew Horton …, 2009-2019 Brendan Coles …`,
  `License: GPL-2.0+`. `usr/lib/ruby/vendor_ruby/whatweb/version.rb` states the same.
- Debian packaging: `Files: debian/*`, `Copyright: 2012- Laszlo Boszormenyi (GCS)
  <gcs@debian.org>, 2011-2012 Guillaume Delacour <gui@iroqwa.org>`, `License: GPL-2.0+`.
- Full licence text on a Debian system: `/usr/share/common-licenses/GPL-2`.

Because WhatWeb is copyleft (GPL-2.0+), redistribution is permitted; the original
copyright notices and licence are preserved inside the package
(`usr/share/doc/whatweb/copyright`).

---

## 11. Verification log (2026-09-26, this workstation)

| Check | Command | Result |
|---|---|---|
| Tracked files | `git ls-tree -r --long HEAD` (at `f12719e`) | 4 files, no `.gitignore`, no `LICENSE` |
| Artifact hashes | `sha256sum <files>` | table in §2 |
| ZIP listing | `unzip -l whatweb_0.5.5-1_all.zip` | 4 entries, total 2,305,964 B (§3) |
| Live mirror | `curl -sI …/whatweb_0.5.5-1_all.deb` | `200 OK`, `Content-Length: 2306152`, `Last-Modified: 2021-01-15` |
| Mirror vs ZIP members | `ar x` + `sha256sum` | 3/3 hashes identical (§3) |
| Byte-identical rebuild | header-preserving `ar` rebuild in Python | `BYTE-IDENTICAL: True`, sha256 `9a9e233d…` |
| `control` metadata | `cat ctl/control` | §4 |
| File counts | `find data -type f \| wc -l` | 1,861 files / 16 dirs |
| Plugin files | `ls plugins \| wc -l`; `ls plugins/*.rb \| wc -l` | 1,821 / 1,818 |
| Plugin registration | `--list-plugins`; loader `.size`; name extraction | 1,824 (duplicate `nopCommerce`) |
| Runtime smoke test | `ruby <scratch>/bin/whatweb --version / --list-plugins / <scan>` | §9 |
| Package page | `curl … packages.debian.org/bullseye/whatweb` | `Package: whatweb (0.5.5-1)` |
| Upstream today | `curl … urbanadventurer/WhatWeb/master/README.md` | latest release v0.6.4, April 3, 2026 |
| Screenshot | `file`; `tesseract … stdout` | 1484x1723 JPEG; OCR = pkgs.org nav sidebar (§8) |

## 12. Re-verification pass (2026-09-27, this workstation)

Every 2026-09-26 value above was re-derived from scratch with the same commands. Results:

| Check | Command re-run | 2026-09-27 result |
|---|---|---|
| Artifact hashes | `sha256sum <4 files>` + `ls -l` | all four hashes **and** byte sizes unchanged (§2) |
| Tracked files | `git ls-files`; `git ls-tree -r --long HEAD` | 5 tracked files (4 + `README.md`), no `LICENSE`, no active `.gitignore` (§2, §7) |
| ZIP listing | `unzip -l whatweb_0.5.5-1_all.zip` | 4 entries, 2,305,964 B total — unchanged (§3) |
| ZIP member hashes | `sha256sum whatweb_0.5.5-1_all/{debian-binary,control.tar.xz,data.tar.xz}` | `d526eb4e…`, `bff79925…`, `3741de8c…` — unchanged (§3) |
| Live Debian mirror | `curl -sI http://ftp.de.debian.org/debian/pool/main/w/whatweb/whatweb_0.5.5-1_all.deb` | `200 OK`, `Content-Length: 2306152`, `Last-Modified: Fri, 15 Jan 2021 21:42:47 GMT`; downloaded `.deb` sha256 `9a9e233d4a5340e9899b44aada049a5212bfae90a98ad7525b7d109f150afd78` — unchanged (§3) |
| Mirror vs ZIP members | `ar x` + `sha256sum` | 3/3 identical — unchanged (§3) |
| Header-preserving rebuild | Python `ar` rebuild reusing the live `.deb`'s headers | `BYTE-IDENTICAL: True` (§3) |
| Plain `ar rc` rebuild | `ar rc` on the three members | same 2,306,152 B, `cmp` differs at byte 22 (name-field `/`, mtime `0`, mode `644`); offsets 21 / 24-35 / 48-55 confirmed byte-by-byte (§3) |
| `control` metadata | `tar -xJf control.tar.xz -C ctl && cat ctl/control` | §4 table unchanged; `md5sums` 1,861 lines |
| Maintainer scripts | `cat ctl/{preinst,postinst,prerm,postrm}` | all four `dh_installdeb/13.3.1`; `postinst` runs the `symlink_to_dir … 0.4.9-2` helper (§4) |
| File/dir counts | `find data -type f \| wc -l`; `find data -type d \| wc -l` | 1,861 files / 16 dirs — unchanged (§5) |
| Unpacked size | `find data -type f -printf '%s\n' \| awk '{s+=$1} END{print s}'` | **18,531,007** — **corrected** from the earlier 18,662,079 (`du -sb`, which adds the 16 dirs' 131,072 B) (§5) |
| Plugin counts | `ls plugins \| wc -l`; `ls plugins/*.rb \| wc -l`; `find usr/share/whatweb -name '*.rb' \| wc -l` | 1,821 / 1,818 / 1,825 — unchanged (§5) |
| Plugin registration | `--list-plugins \| grep '^Total'`; loader `.size`; name regex | 1,824; 1,824; `total 1825 unique 1824 dups {'nopCommerce': 2}` — unchanged (§5) |
| Bundled badge | `zcat …/README.md.gz \| grep plugins-` | `plugins-1824` — unchanged (§5) |
| Package page | `curl -s … packages.debian.org/bullseye/whatweb` | `<title>Debian -- Details of package whatweb in bullseye</title>` + `Package: whatweb (0.5.5-1)` (§3) |
| Upstream release | `curl -s … urbanadventurer/WhatWeb/master/README.md` | `Latest Release: v0.6.4. April 3, 2026` — unchanged (§1) |
| Upstream changelog | `zcat data/usr/share/doc/whatweb/changelog.gz` | `Version 0.5.5 - January 16, 2021` (§1) |
| Page capture integrity | `git show f12719e:"src/Next generation web scanner.md" \| sha256sum`; `wc -c` | `219c59d0…`, 3,737 B; `diff` against the current file minus its 3-line header is **empty** (§6) |
| `.src/jpeg` provenance | `diff -u <(git show fd58e04:.gitignore) .src/jpeg`; per-commit `wc -lc` | original was 13 lines / 75 B; the file is a mangled 24-line / 316 B descendant — **§7 corrected** |
| Screenshot OCR | `tesseract … stdout`; grep counts | 1,217 OCR chars; sidebar names present, `whatweb` / `0.5.5` absent (§8) |
| Runtime | `ruby /tmp/wws/bin/whatweb --version / --list-plugins / <scan>` | `0.5.5`, `Total: 1824 Plugins`, real 200/401 split on `:18900` — **entry point correct in §9** |
| Stack ports | `curl -s -m 3 -o /dev/null -w '%{http_code}' http://127.0.0.1:<port>/health` | only `18900` → `200`; the other 12 → `000`, so the two 2026-09-26 scans are labelled not-reproducible (§9) |
| Installed gems | `gem list` | `addressable (2.9.0)`, `ipaddress (0.8.3)`, `json (default: 2.5.1)`; no `rchardet` (§9) |

Three claims were **wrong** and are fixed above: the unpacked size (§5), the `.src/jpeg`
provenance and "three extra lines" (§7), and the non-existent `whatweb-cli` entry point
(§5, §9, §11). Everything else re-derived to the same value.
