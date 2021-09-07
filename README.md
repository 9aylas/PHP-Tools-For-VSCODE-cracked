# PHP-Tools-For-VSCODE (cracked extension)

- i'm using windows so the path is :
 %USERPROFILE%\.vscode\extensions\devsense.phptools-vscode-1.4.7295\out\src
- backup extension.js original file, and replace it with this code .
```javascript
"use strict";
var e = this && this.t || function(e, t, i, n) {
    return new(i || (i = Promise))(function(o, r) {
        function s(e) {
            try {
                l(n.next(e))
            } catch (e) {
                r(e)
            }
        }

        function u(e) {
            try {
                l(n.throw(e))
            } catch (e) {
                r(e)
            }
        }

        function l(e) {
            var t;
            e.done ? o(e.value) : (t = e.value, t instanceof i ? t : new i(function(e) {
                e(t)
            })).then(s, u)
        }
        l((n = n.apply(e, t || [])).next())
    })
};
Object.defineProperty(exports, "__esModule", {
    value: !0
}), exports.o = exports.s = exports.tailmessage = exports.u = void 0;
const t = require("vscode"),
    h = require("./debug/ConfigurationProvider"),
    g = require("vscode-languageclient/node"),
    m = require("os"),
    w = require("xmlhttprequest"),
    y = require("child_process"),
    P = require("./downloader/FileDownloader"),
    b = require("./downloader/NetworkSettings"),
    q = require("fs"),
    H = require("path"),
    S = require("./embeddedContentDocuments"),
    T = require("./embeddedPhar"),
    O = require("./utils"),
    $ = require("./telemetry"),
    k = require("events"),
    E = require("./Resource"),
    D = require("vscode-test-adapter-api"),
    F = require("vscode-test-adapter-util"),
    N = require("./testadapter/phptestadapter");
let I = new k.EventEmitter,
    L = "Cracked By 9aylas";
const C = "DEVSENSE.phptools-vscode",
    _ = "phptools.selectPhpVersion";
let M;
const j = "dotnet";
let z, R, J = {
    phpbin: void 0,
    version: void 0,
    l: void 0
};
const K = new Map;
let A, V = 0;

function X(e) {
    return E.GlobalResources.Get().GetString(__filename, e)
}

function U(e) {
    return X(e)
}

function G() {
    return L
}
var W;

function B(i) {
    return e(this, void 0, void 0, function*() {
        exports.u = i, $.p();
        let e = JSON.parse(q.readFileSync(i.asAbsolutePath("package.json"), "utf8")).contributes.configuration.properties["phpTools.language"].enum;
        if (E.GlobalResources.InitGlobalResources(i.asAbsolutePath("locale"), e), (M = t.window.createOutputChannel("PHP")).appendLine(X("phpToolsStarted")), i.subscriptions.push(t.commands.registerCommand("phptools.activate", () => Qe())), i.subscriptions.push(t.commands.registerCommand(_, () => de())), i.subscriptions.push(R = t.window.createStatusBarItem(t.StatusBarAlignment.Right, 99)), i.subscriptions.push(A = t.window.createStatusBarItem(t.StatusBarAlignment.Left, 0)), i.subscriptions.push(t.window.onDidChangeActiveTextEditor(e => {
                te(e ? e.document : null)
            })), !oe()) {
            const e = "mute.missingphp";
            if (!i.globalState.get(e)) {
                const n = X("dontshowagain"),
                    o = X("dismiss");
                t.window.showWarningMessage("The `php` command cannot be found. Please verify that PHP is installed, or set the `php.executables` setting.", o, n).then(t => {
                    t == n && i.globalState.update(e, !0)
                })
            }
        }
        I.on("active", () => L = ""), I.on("inactive", () => L = "Cracked By 9aylas"), Z(), ce(), ge(i).then(e => {
            z = e, i.subscriptions.push(z.start());
            const n = new h.PhpDebugConfigurationProvider(z);
            i.subscriptions.push(t.debug.registerDebugConfigurationProvider("php", n)), i.subscriptions.push(n), i.subscriptions.push(pe()), i.subscriptions.push(t.commands.registerCommand("phpTools.debug.startWithStopOnEntry", h.startDebuggingAndStopOnEntry)), i.subscriptions.push(T.initializeEmbeddedPharDocuments(z)), z.onReady().then(() => {
                z.onNotification("devsense/loadStatus", e => {
                    V = (V + 1) % 2, A.tooltip = "Processing workspace changes ...";
                    let t = V ? "$(circle-filled)" : "$(circle-outline)";
                    e.isLoadPending ? (A.text = `${t} Processing ${e.pendingParse+e.pendingAnalysis} …`, A.show()) : e.pendingAnalysis > 100 ? (A.text = t, A.show()) : A.hide()
                })
            }), M.appendLine("PHP language server started."), ut(i)
        }), Ge(), M.appendLine(L)
    })
}

function Q() {
    return e(this, void 0, void 0, function*() {
        z && (yield z.stop()), $.client.trackEvent({
            name: "extension unloaded"
        })
    })
}

function Y(e) {
    var t, i;
    if (e.packageJSON && e.packageJSON.activationEvents && e.packageJSON.activationEvents.indexOf("onLanguage:php") >= 0) return !0;
    let n = null === (i = null === (t = e.packageJSON) || void 0 === t ? void 0 : t.contributes) || void 0 === i ? void 0 : i.debuggers;
    return !(!n || !n.find(e => {
        var t;
        return "php" == e.type || (null !== (t = e.languages) && void 0 !== t ? t : []).indexOf("php") >= 0
    }))
}

function Z() {
    return e(this, void 0, void 0, function*() {
        let e = t.extensions.all,
            i = [C, "codingyu.laravel-goto-view", "vscode.php-language-features", "chinchiheather.vscode-margin-colours", "aaron-bond.better-comments", "phproberto.vscode-php-getters-setters", "junstyle.php-cs-fixer", "ikappas.phpcs", "chrmarti.regex", "johnbillion.vscode-wordpress-hooks", "SonarSource.sonarlint-vscode", "persoderlind.vscode-phpcbf", "iolevel.peachpie-vscode", "anteprimorac.html-end-tag-labels", "ecmel.vscode-html-css"],
            n = e.filter(e => e && !e.id.startsWith("vscode.") && Y(e) && i.indexOf(e.id) < 0);
        if (exports.u.globalState.get("suppress.extensions.check") != n.length && (exports.u.globalState.update("suppress.extensions.check", 0), 0 != n.length)) {
            const e = X("extensions"),
                i = X("dontshowagain");
            let o;
            switch (o = "Following extensions should be disabled since their features overlaps with PHP Tools: " + n.map(e => {
                    var t;
                    return `${null===(t=e.packageJSON)||void 0===t?void 0:t.displayName} (${e.id})`
                }).join(", "), yield t.window.showErrorMessage(o, e, i)) {
                case e:
                    yield t.commands.executeCommand("workbench.view.extensions");
                    break;
                case i:
                    exports.u.globalState.update("suppress.extensions.check", n.length)
            }
        }
    })
}

function ee() {
    if ("osx" == ue()) return M.appendLine("Info: Using extra package on macOS."), !1;
    let e = y.spawnSync(j, ["--list-runtimes"], {
        encoding: "utf8"
    });
    if (!e.output) return M.appendLine("Info: 'dotnet' runtime is missing."), !1;
    if (e.output.join("\n").indexOf("Microsoft.NETCore.App 5.0") >= 0) return M.appendLine("Found .NET 5.0."), !0;
    M.appendLine("Found .NET Runtime (but required version 5.0 is missing).")
}

function te(e) {
    null != e && void 0 != e && "php" == e.languageId.toLowerCase() ? R.show() : R.hide()
}

function ie(e, i = null) {
    if (i) {
        let e = i.indexOf("-");
        e && e > 0 && (i = i.substr(0, e))
    } else i = "8.0";
    R.tooltip = e || "PHP executable", R.text = i, R.command = _, te(t.window.activeTextEditor ? t.window.activeTextEditor.document : null)
}

function ne(e) {
    if (e) {
        let o = K[e];
        if (o) return o;
        let r = y.spawnSync(e, ["--version"], {
            encoding: "utf8",
            timeout: 3e3
        });
        if (r.output) {
            var t = r.output.join(""),
                i = /^PHP\s([\d\.a-z\-]+)/g.exec(t);
            if (i && i[1]) {
                var n = /with Xdebug v([\d\.a-z\-]+)/.exec(t);
                return K[e] = o = {
                    phpbin: e,
                    version: i[1],
                    l: n ? n[1] : void 0
                }, o
            }
        }
    }
}

function oe() {
    let e = ve(),
        i = ne(e);
    return i ? (M.appendLine(`Found PHP, version: ${i.version}, Xdebug: ${i.l||"not loaded"}.`), "3.0.0" == i.l && t.window.showInformationMessage("Recommending to update Xdebug PHP extension. Xdebug 3.0.0 may cause issues during debugging."), J = i, ie(e, i.version), $.client.trackEvent({
        name: "has php",
        properties: {
            "php-version": i.version,
            "xdebug-version": i.l || "none"
        }
    }), !0) : (ie(e), J = {
        version: t.workspace.getConfiguration().get("php.version"),
        phpbin: void 0
    }, $.client.trackEvent({
        name: "no php",
        properties: {}
    }), M.appendLine(`Notice: PHP cannot be found in '${e}'.`), !1)
}

function re(i, n) {
    return e(this, void 0, void 0, function*() {
        let e = `${ue()}-${le()}-${se()}`,
            o = H.join(n, "Devsense.PHP.LanguageServer"),
            r = `https://devsenseblob.azureedge.net/phptools/vscode/${e}.zip`,
            s = {
                name: "downloading runtime",
                url: r,
                resultCode: 0,
                success: !1,
                duration: 0
            };
        if (!q.existsSync(H.join(n, "phptools-verify"))) {
            M.show(!0);
            let l = +new Date;
            try {
                let l = yield P.DownloadFile(`PHP Tools dependencies (${e})`, M, b.vscodeNetworkSettingsProvider(), r);
                q.writeFileSync(i, l);
                var u = require("extract-zip");
                M.appendLine(`Installing package '${e}'`), yield u(i, {
                    dir: n
                }), "win" != ue() && q.chmodSync(o, 365), q.unlink(i, e => {}), s.success = !0, q.existsSync(o) || q.existsSync(o + ".exe") ? M.appendLine("Finished.\n") : M.appendLine("Download failed.\n")
            } catch (e) {
                s.success = !1, M.appendLine(e);
                const i = X("download");
                t.window.showErrorMessage("The extension requires 'dotnet' runtime for full functionality.", i).then(e => {
                    e == i && require("open")("https://www.microsoft.com/net/download")
                })
            }
            s.duration = +new Date - l, $.client.trackRequest(s)
        }
    })
}

function se() {
    return t.extensions.getExtension(C).packageJSON.version
}

function ue() {
    var e = process.platform;
    return "darwin" == e ? "osx" : "win32" == e ? "win" : "linux" == e ? "linux" : void 0
}

function le() {
    var e = process.platform;
    if ("darwin" == e) return "x64";
    var t = require("os").arch();
    return "win32" != e || "x32" != t && "ia32" != t ? t : "x86"
}

function ce() {
    let e = t.workspace.getConfiguration();
    e.update("php.suggest.basic", !1, t.ConfigurationTarget.Global), e.update("php.validate.enable", !1, t.ConfigurationTarget.Global);
    let i = e.get("emmet.excludeLanguages"); - 1 == i.indexOf("php") && e.update("emmet.excludeLanguages", i.concat(["php"]), t.ConfigurationTarget.Global)
}

function ae(e) {
    let t = e.get("php.problems.scope");
    if ("string" == typeof t && t) return t;
    let i = e.get("php.problems.workspaceAnalysis");
    return "boolean" != typeof i || i ? "user" : "none"
}

function pe() {
    return t.workspace.onDidChangeConfiguration(e => {
        let i = t.workspace.getConfiguration(),
            n = {};
        e.affectsConfiguration("phpTools.language") && (n["phpTools.language"] = i.get("phpTools.language") || t.env.language), e.affectsConfiguration("php.problems.exclude") && (n["php.problems.exclude"] = i.get("php.problems.exclude")), e.affectsConfiguration("files.exclude") && (n["files.exclude"] = i.get("files.exclude")), e.affectsConfiguration("php.format.codeStyle") && (n["php.format.codeStyle"] = i.get("php.format.codeStyle")), e.affectsConfiguration("php.format.autoimport") && (n["php.format.autoimport"] = i.get("php.format.autoimport")), (e.affectsConfiguration("php.executablePath") || e.affectsConfiguration("php.executables") || e.affectsConfiguration("php.version")) && (oe(), n["php.version"] = J.version), (e.affectsConfiguration("php.problems.workspaceAnalysis") || e.affectsConfiguration("php.problems.scope")) && (n["php.problems.scope"] = ae(i)), 0 != Object.keys(n).length && z.sendNotification(g.DidChangeConfigurationNotification.type, {
            settings: n
        })
    })
}

function de() {
    let e = he(),
        i = [];
    Object.keys(e).forEach(t => {
        let n = e[t];
        i.push({
            label: t,
            description: "",
            detail: n,
            picked: n == J.phpbin
        })
    }), t.window.showQuickPick(i, {
        canPickMany: !1,
        placeHolder: X("pickPhpVersion")
    }).then(e => {
        if (e) {
            t.workspace.getConfiguration().update("php.version", e.label)
        }
    })
}

function he(e = !1) {
    let i = t.workspace.getConfiguration().get("php.executables", {});
    if (e) return i;
    const n = ["", "5.4", "5.5", "5.6", "7.0", "7.1", "7.2", "7.3", "7.4", "8.0", "8.1"];
    let o = [],
        r = {};
    if ("win" == ue()) {
        let e = [];
        e.push(process.env.h, process.env.PHPRC), ["C:\\Program Files\\PHP", "C:\\Program Files (x86)\\PHP", "C:\\Program Files\\IIS Express\\PHP", "C:\\Program Files (x86)\\IIS Express\\PHP"].forEach(t => {
            try {
                q.readdirSync(t, {
                    withFileTypes: !0
                }).forEach(i => {
                    i.isFile() && "php.exe" == i.name ? e.push(t) : i.isDirectory() && e.push(t + "\\" + i.name)
                })
            } catch (e) {}
        }), o = e.filter(e => e).map(e => e + "\\php.exe")
    } else(o = n.map(e => "/usr/bin/php" + e)).push("/opt/lampp/bin/php");
    return o.forEach(e => {
        let t = ne(e);
        t && (r[t.version] = e)
    }), Object.assign(Object.assign({}, r), i)
}

function ve() {
    let e = t.workspace.getConfiguration();
    return fe(e.get("php.version"), e.get("php.executablePath") || "php")
}

function fe(e, t) {
    if (e) {
        if ("string" == typeof J.version && J.version.startsWith(e) && J.phpbin) return J.phpbin;
        let t = he(!0);
        if (t && t[e]) return t[e];
        let i = void 0,
            n = void 0,
            o = void 0;
        t = he(!1), Object.keys(t).forEach(r => {
            r == e && (i = t[r]), r.startsWith(e) && (n = t[r]), e.startsWith(r) && (o = t[r]);
            let s = e.split(".");
            s.length > 2 && r.startsWith(`${s[0]}.${s[1]}`) && (o = t[r])
        });
        let r = i || n || o;
        if (r) return r;
        M.appendLine(`Couldn't resolve requested PHP version '${e}' ... using default`)
    }
    return t || J.phpbin || "php"
}

function ge(e) {
    return me(e).then(e => {
        let i = {
                run: {
                    command: e.command,
                    args: e.args,
                    options: {
                        env: {
                            MALLOC_TRIM_THRESHOLD_: 1e5
                        }
                    }
                },
                debug: {
                    command: e.command,
                    args: e.args.concat(["--debug"])
                }
            },
            n = S.initializeEmbeddedContentDocuments(() => z),
            o = t.workspace.getConfiguration(),
            r = {
                documentSelector: [{
                    language: "php"
                }],
                initializationOptions: {
                    "files.associations": o.get("files.associations"),
                    "files.exclude": o.get("files.exclude"),
                    "php.problems.exclude": o.get("php.problems.exclude"),
                    "phpTools.language": o.get("phpTools.language") || t.env.language,
                    "php.format.codeStyle": o.get("php.format.codeStyle"),
                    "php.format.autoimport": o.get("php.format.autoimport"),
                    "php.problems.scope": ae(o),
                    "php.version": J.version
                },
                synchronize: {
                    fileEvents: t.workspace.createFileSystemWatcher("{**/*.php,**/*.phar}")
                },
                middleware: n.middleware
            };
        return new g.LanguageClient("PHP Language Server", i, r)
    })
}

function me(e) {
    let t = e.asAbsolutePath("out/server/Devsense.PHP.LanguageServer");
    return ee() ? Promise.resolve({
        command: j,
        args: [t + ".dll"]
    }) : re(e.asAbsolutePath("out.zip"), e.asAbsolutePath("out/server")).then(() => Promise.resolve({
        command: t,
        args: []
    }))
}
exports.tailmessage = G,
    function(e) {
        e[e.Missing = 0] = "Missing", e[e.Expired = 2] = "Expired", e[e.Valid = 2] = "Valid", e[e.Invalid = 2] = "Valid"
    }(W || (W = {})), exports.activate = B, exports.deactivate = Q, exports.s = fe, exports.o = ge;
let xe = [45, 45, 45, 45, 45, 66, 69, 71, 73, 78, 32, 80, 85, 66, 76, 73, 67, 32, 75, 69, 89, 45, 45, 45, 45, 45, 10, 77, 73, 71, 102, 77, 65, 48, 71, 67, 83, 113, 71, 83, 73, 98, 51, 68, 81, 69, 66, 65, 81, 85, 65, 65, 52, 71, 78, 65, 68, 67, 66, 105, 81, 75, 66, 103, 81, 67, 118, 67, 119, 109, 55, 98, 72, 43, 79, 117, 73, 70, 67, 77, 102, 68, 85, 79, 48, 121, 86, 85, 84, 104, 73, 10, 90, 113, 50, 116, 122, 50, 84, 81, 73, 50, 85, 100, 50, 80, 103, 69, 107, 104, 55, 74, 100, 111, 51, 51, 80, 77, 49, 50, 67, 76, 66, 108, 71, 86, 89, 106, 105, 107, 82, 65, 100, 112, 75, 118, 104, 105, 115, 66, 48, 101, 43, 102, 47, 51, 119, 43, 73, 116, 56, 109, 115, 74, 114, 67, 10, 86, 84, 114, 120, 75, 116, 88, 116, 65, 70, 83, 115, 83, 55, 51, 83, 110, 110, 98, 121, 74, 89, 121, 105, 120, 114, 115, 69, 67, 65, 85, 121, 101, 116, 122, 99, 71, 52, 116, 54, 52, 47, 48, 57, 108, 74, 117, 110, 79, 97, 85, 106, 71, 98, 74, 80, 50, 87, 116, 106, 51, 47, 116, 50, 10, 57, 90, 99, 67, 122, 119, 68, 85, 84, 89, 81, 43, 56, 56, 78, 102, 48, 81, 73, 68, 65, 81, 65, 66, 10, 45, 45, 45, 45, 45, 69, 78, 68, 32, 80, 85, 66, 76, 73, 67, 32, 75, 69, 89, 45, 45, 45, 45, 45];
const we = [89, 111, 117, 114, 32, 99, 111, 112, 121, 32, 111, 102, 32, 80, 72, 80, 32, 84, 111, 111, 108, 115, 32, 105, 115, 32, 110, 111, 116, 32, 97, 99, 116, 105, 118, 97, 116, 101, 100, 46, 32, 80, 108, 101, 97, 115, 101, 32, 101, 110, 116, 101, 114, 32, 121, 111, 117, 114, 32, 108, 105, 99, 101, 110, 115, 101, 32, 107, 101, 121, 46],
    ye = [89, 111, 117, 114, 32, 99, 117, 114, 114, 101, 110, 116, 32, 108, 105, 99, 101, 110, 115, 101, 32, 104, 97, 115, 32, 101, 120, 112, 105, 114, 101, 100, 46, 32, 80, 108, 101, 97, 115, 101, 32, 101, 110, 116, 101, 114, 32, 97, 32, 110, 101, 119, 32, 108, 105, 99, 101, 110, 115, 101, 32, 107, 101, 121, 46],
    Pe = [73, 32, 104, 97, 118, 101, 32, 116, 104, 101, 32, 108, 105, 99, 101, 110, 115, 101, 32, 107, 101, 121],
    be = [71, 101, 116, 32, 116, 114, 105, 97, 108],
    qe = [89, 111, 117, 114, 32, 101, 45, 109, 97, 105, 108],
    He = [80, 108, 101, 97, 115, 101, 32, 101, 110, 116, 101, 114, 32, 121, 111, 117, 114, 32, 101, 45, 109, 97, 105, 108, 32, 97, 100, 100, 114, 101, 115, 115, 46, 32, 89, 111, 117, 32, 119, 105, 108, 108, 32, 114, 101, 99, 101, 105, 118, 101, 32, 116, 104, 101, 32, 116, 114, 105, 97, 108, 32, 108, 105, 99, 101, 110, 115, 101, 32, 107, 101, 121, 32, 105, 110, 32, 97, 32, 102, 101, 119, 32, 109, 105, 110, 117, 116, 101, 115, 46, 32, 70, 111, 114, 32, 109, 111, 114, 101, 32, 105, 110, 102, 111, 114, 109, 97, 116, 105, 111, 110, 32, 118, 105, 115, 105, 116, 32, 119, 119, 119, 46, 100, 101, 118, 115, 101, 110, 115, 101, 46, 99, 111, 109],
    Se = [63, 109, 101, 116, 104, 111, 100, 61, 116, 114, 105, 97, 108, 95, 118, 115, 99, 111, 100, 101],
    Te = [38, 109, 97, 105, 108, 61],
    Oe = [69, 110, 116, 101, 114, 101, 100, 32, 101, 45, 109, 97, 105, 108, 32, 105, 115, 32, 110, 111, 116, 32, 118, 97, 108, 105, 100],
    $e = [77, 111, 114, 101, 32, 105, 110, 102, 111, 114, 109, 97, 116, 105, 111, 110],
    ke = [80, 117, 114, 99, 104, 97, 115, 101],
    Ee = [80, 108, 101, 97, 115, 101, 32, 101, 110, 116, 101, 114, 32, 121, 111, 117, 114, 32, 108, 105, 99, 101, 110, 115, 101, 32, 107, 101, 121, 46, 32, 73, 116, 32, 119, 105, 108, 108, 32, 98, 101, 32, 97, 99, 116, 105, 118, 97, 116, 101, 100, 32, 111, 110, 108, 105, 110, 101, 46, 32, 70, 111, 114, 32, 109, 111, 114, 101, 32, 105, 110, 102, 111, 114, 109, 97, 116, 105, 111, 110, 32, 118, 105, 115, 105, 116, 32, 119, 119, 119, 46, 100, 101, 118, 115, 101, 110, 115, 101, 46, 99, 111, 109],
    De = [76, 105, 99, 101, 110, 115, 101, 32, 75, 101, 121],
    Fe = [104, 116, 116, 112, 115, 58, 47, 47, 119, 119, 119, 46, 100, 101, 118, 115, 101, 110, 115, 101, 46, 99, 111, 109, 47, 112, 117, 114, 99, 104, 97, 115, 101, 63, 102, 114, 111, 109, 61, 118, 115, 99, 111, 100, 101],
    Ne = [76, 105, 99, 101, 110, 115, 101, 32, 105, 110, 118, 97, 108, 105, 100, 32, 111, 114, 32, 101, 120, 112, 105, 114, 101, 100, 46],
    Ie = [67, 111, 110, 110, 101, 99, 116, 105, 111, 110, 32, 116, 111, 32, 97, 99, 116, 105, 118, 97, 116, 105, 111, 110, 32, 115, 101, 114, 118, 101, 114, 32, 116, 105, 109, 101, 111, 117, 116, 101, 100, 46],
    Le = [65, 99, 116, 105, 118, 97, 116, 105, 111, 110, 32, 115, 101, 114, 118, 101, 114, 32, 99, 97, 110, 110, 111, 116, 32, 98, 101, 32, 114, 101, 97, 99, 104, 101, 100, 46],
    Ce = [65, 99, 116, 105, 118, 97, 116, 105, 111, 110, 32, 101, 114, 114, 111, 114, 46],
    _e = [65, 99, 116, 105, 118, 97, 116, 105, 111, 110, 32, 115, 101, 114, 118, 101, 114, 32, 105, 115, 32, 117, 110, 97, 118, 97, 105, 108, 97, 98, 108, 101, 32, 97, 116, 32, 116, 104, 105, 115, 32, 116, 105, 109, 101, 46],
    Me = [65, 99, 116, 105, 118, 97, 116, 105, 111, 110, 32, 115, 101, 114, 118, 101, 114, 32, 105, 110, 116, 101, 114, 110, 97, 108, 32, 101, 114, 114, 111, 114, 46],
    je = [69, 110, 116, 101, 114, 101, 100, 32, 108, 105, 99, 101, 110, 115, 101, 32, 107, 101, 121, 32, 105, 115, 32, 110, 111, 116, 32, 118, 97, 108, 105, 100, 46],
    ze = [104, 116, 116, 112, 115, 58, 47, 47, 97, 112, 105, 46, 100, 101, 118, 115, 101, 110, 115, 101, 46, 99, 111, 109, 47, 108, 105, 99, 101, 110, 115, 101, 47],
    Re = [104, 116, 116, 112, 115, 58, 47, 47, 119, 119, 119, 46, 100, 101, 118, 115, 101, 110, 115, 101, 46, 99, 111, 109, 47, 112, 117, 114, 99, 104, 97, 115, 101, 47, 108, 105, 99, 101, 110, 115, 101],
    Je = [65, 99, 116, 105, 118, 97, 116, 105, 111, 110, 32, 115, 117, 99, 99, 101, 101, 100, 101, 100, 44, 32, 116, 104, 97, 110, 107, 32, 121, 111, 117, 32, 102, 111, 114, 32, 117, 115, 105, 110, 103, 32, 80, 72, 80, 32, 84, 111, 111, 108, 115, 33],
    Ke = [63, 109, 101, 116, 104, 111, 100, 61, 97, 99, 116, 105, 118, 97, 116, 101, 95, 118, 115, 99, 111, 100, 101],
    Ae = [38, 109, 97, 99, 104, 105, 110, 101, 95, 105, 100, 61],
    Ve = [38, 107, 101, 121, 61],
    Xe = [110, 111, 100, 101, 45, 114, 115, 97],
    Ue = [112, 104, 112, 84, 111, 111, 108, 115, 46, 108, 105, 99, 101, 110, 115, 101];

function Ge() {
    return e(this, void 0, void 0, function*() {
        (yield it()) == W.Valid ? I.emit("active") : yield We()
    })
}

function We() {
    return e(this, void 0, void 0, function*() {
        let e, i = yield tt();
        e = i && (yield st(i)) ? [X("expired"), X("enterKey"), X("purchase")] : [X("activationMessage"), X("enterKey"), X("requestTrial"), X("info")], yield Be(yield t.window.showInformationMessage.apply("", e))
    })
}

function Be(t) {
    return e(this, void 0, void 0, function*() {
        t == X("info") || t == X("purchase") ? (et(), yield We()) : t == X("requestTrial") ? yield Ye(): t == X("enterKey") && (yield Qe())
    })
}

function Qe() {
    return e(this, void 0, void 0, function*() {
        let e = yield t.window.showInputBox({
            prompt: X("promptText"),
            placeHolder: X("placeHolder"),
            ignoreFocusOut: !0
        });
        if (e) {
            let t = void 0;
            if (e.length > 32) try {
                JSON.parse(e).signature && (t = e)
            } catch (e) {
                t = void 0
            }
            t || (t = yield rt(O.v(Ke), O.v(Ve), new(require(O.v(Xe)))(O.v(xe)).encrypt(e, "base64").replace(/\+/g, "-").replace(/\//g, "|").replace(/=/g, "_"))), t && (yield ot(t))
        } else We()
    })
}

function Ye() {
    return e(this, void 0, void 0, function*() {
        let e = yield t.window.showInputBox({
            prompt: X("trialPrompt"),
            placeHolder: X("trialMail"),
            ignoreFocusOut: !0,
            validateInput: e => /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(e) ? null : X("invalidMail")
        });
        if (e) {
            let t = yield rt(O.v(Se), O.v(Te), e);
            t && (yield Ze(t))
        } else yield We()
    })
}

function Ze(i) {
    return e(this, void 0, void 0, function*() {
        try {
            let e = JSON.parse(i);
            $.client.trackEvent({
                name: "trial requested"
            }), (yield t.window.showInformationMessage(e.message, X("enterKey"))) ? yield Qe(): yield We()
        } catch (e) {
            t.window.showErrorMessage("Invalid Response")
        }
    })
}

function et() {
    return e(this, void 0, void 0, function*() {
        require("open")(O.v(Fe))
    })
}

function tt() {
    return e(this, void 0, void 0, function*() {
        try {
            return JSON.parse(exports.u.globalState.get("9aylas" + "." + m.userInfo().username) || exports.u.globalState.get(O.v(Ue)) || t.workspace.getConfiguration().get(O.v(Ue)))
        } catch (e) {
            return
        }
    })
}

function it() {
    return e(this, void 0, void 0, function*() {
        let e = yield tt();
        if (e) {
            var t = require(O.v(O.g))(m.userInfo().username) + "#" + e.license + "#" + e.expiration;
            return new(require(O.v(Xe)))(O.v(xe)).verify(t, e.signature, "utf8", "base64") ? (yield st(e)) ? W.Expired : W.Valid : W.Invalid
        }
        return I.emit("active"), W.Valid
    })
}

function nt(i, n) {
    return e(this, void 0, void 0, function*() {
        const e = O.v(Re) + n;
        M.appendLine(i), n && (M.appendLine("Notice: If you have issues accessing our server, open following URL in a web browser:"), M.appendLine(e));
        const o = X("retry"),
            r = n ? X("activateOffline") : void 0;
        let s = yield t.window.showErrorMessage(i, o, r);
        s == o ? Qe() : s == r && r && require("open")(e)
    })
}

function ot(i) {
    return e(this, void 0, void 0, function*() {
        try {
            JSON.parse(i), exports.u.globalState.update(O.v(Ue) + "." + m.userInfo().username, i), M.appendLine(X("licenseStored")), (yield it()) == W.Valid ? (t.window.showInformationMessage(X("activationSucceeded")), $.client.trackEvent({
                name: "extension activated"
            }), I.emit("active")) : ($.client.trackEvent({
                name: "extension activation error"
            }), I.emit("inactive"))
        } catch (e) {
            M.appendLine(X("licenseError")), t.window.showErrorMessage(X("invalidLicenseKey")), $.client.trackException({
                exception: e
            }), We()
        }
    })
}

function rt(t, i, n) {
    return e(this, void 0, void 0, function*() {
        if (!n) return;
        let e = t + O.v(Ae) + require(O.v(O.g))(m.userInfo().username) + i + n,
            o = O.v(ze) + e,
            r = new w.XMLHttpRequest;
        var s = +new Date;
        return r.open("GET", o, !0), new Promise(i => {
            r.onreadystatechange = function() {
                if (4 == this.readyState) {
                    var n = +new Date - s;
                    if ($.client.trackRequest({
                            name: t,
                            url: o,
                            duration: n,
                            resultCode: this.status,
                            success: 200 == this.status
                        }), 200 == this.status) i(this.responseText);
                    else {
                        var r;
                        if (r = 404 == this.status || 401 == this.status ? X("invalidLicenseKey") : 403 == this.status ? X("accessDenied") : 500 == this.status ? X("internalError") : 0 == this.status ? X("connectionError") : X("unknownError"), this.responseText) try {
                            let e = JSON.parse(this.responseText);
                            e.message && (r = e.message)
                        } catch (e) {}
                        nt(r, 500 == this.status || 0 == this.status ? e : void 0), i(void 0)
                    }
                }
            }, r.ontimeout = (() => {
                nt(X("serverTimeout"), e), i(void 0)
            }), r.timeout = 5e3, r.send()
        })
    })
}

function st(t) {
    return e(this, void 0, void 0, function*() {
        return new Date > new Date(t.expiration)
    })
}

function ut(i) {
    return e(this, void 0, void 0, function*() {
        const e = t.extensions.getExtension(D.testExplorerExtensionId),
            n = t.window.createOutputChannel("PHP (PHPUnit)");
        if (e) {
            const t = e.exports;
            i.subscriptions.push(new F.TestAdapterRegistrar(t, e => new N.PhpTestAdapter(i, z, e, n)))
        } else n.appendLine("TestHub is not installed. Text Explorer extension is required to show tests.")
    })
}
```

- enjoy :)
