# uWebSockets.js for FreeBSD

![FreeBSD](https://img.shields.io/badge/FreeBSD-AB2B28?style=flat&logo=freebsd&logoColor=white)

Unofficial FreeBSD x64 builds of [uWebSockets.js](https://github.com/uNetworking/uWebSockets.js), a scalable WebSocket and HTTP server for Node.js.

This project is not affiliated with uWebSockets.js, and FreeBSD remains an unsupported upstream platform.

## Automated releases

The [GitHub Actions workflow](.github/workflows/build.yml) checks the latest upstream release every day. When this repository does not have the matching release, it:

1. resolves the source commit recorded by the upstream binary release;
2. builds uWebSockets.js in a FreeBSD 15 x64 virtual machine;
3. smoke-tests the addon with Node.js 24; and
4. publishes every generated `uws_freebsd_x64_<ABI>.node` file under the matching upstream version.

The workflow can also be run manually for a specific upstream version. GitHub's automatically provided `GITHUB_TOKEN` is the only credential it needs.

## Using a build

Download the asset whose filename matches `process.versions.modules`, then place it beside the installed uWebSockets.js `uws.js` loader. The uWebSockets.js version and this project's release version should match exactly.

For example, Node.js ABI `137` needs:

```text
uws_freebsd_x64_137.node
```

## License

Apache-2.0, matching uWebSockets.js and the original FreeBSD build project.
