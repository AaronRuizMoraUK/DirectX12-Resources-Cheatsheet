# DirectX11 Resources Cheatsheet

Table with DirectX 11 Resources, with their respectives Resource Views, Shader data structures and register types.

<!--
<table>
    <thead>
        <tr>
            <th>Layer 1</th>
            <th>Layer 2</th>
            <th>Layer 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=4>L1 Name</td>
            <td rowspan=2>L2 Name A</td>
            <td>L3 Name A</td>
        </tr>
        <tr>
            <td>L3 Name B</td>
        </tr>
        <tr>
            <td rowspan=2>L2 Name B</td>
            <td>L3 Name C</td>
        </tr>
        <tr>
            <td>L3 Name D</td>
        </tr>
    </tbody>
</table>
-->

<table>
    <thead>
        <tr>
            <th>Resource</th>
            <th>Resource View</th>
            <th>Shader (HLSL)</th>
            <th>Shader Register Type</th>
        </tr>
    </thead>
    <tbody>
        <!-- VERTEX BUFFER -->
        <tr>
            <td>Vertex Buffer</td>
            <td>-</td>
            <td>-</td>
            <td> </td>
        </tr>
        <!-- INDEX BUFFER -->
        <tr>
            <td>Index Buffer</td>
            <td>-</td>
            <td>-</td>
            <td> </td>
        </tr>
        <!-- TEXTURE -->
        <tr>
            <td rowspan=4>Texture</td>
            <td>Shader Resource View (read only)</td>
            <td><code>Texture&lt;type&gt;</code></td>
            <td><code>t</code></td>
        </tr>
        <tr>
            <td>Unordered Access View (read/write)</td>
            <td><code>RWTexture&lt;type&gt;</code> <br><br> <code>RasterizerOrderedTexture&lt;type&gt</code></td>
            <td><code>u</code></td>
        </tr>
        <tr>
            <td>Render Target View</td>
            <td>-<type></td>
            <td> </td>
        </tr>
        <tr>
            <td>Depth Stencil View</td>
            <td>-<type></td>
            <td> </td>
        </tr>
        <!-- BUFFER -->
        <tr>
            <td rowspan=3>Buffer</td>
            <td>-</td>
            <td><code>cbuffer {members}</code> <br><br> <code>tbuffer {members}</code></td>
            <td><code>b</code></td>
        </tr>
        <tr>
            <td>Shader Resource View (read only)</td>
            <td><code>Buffer&lt;type&gt;</code> <br><br> <code>StructuredBuffer&lt;struct&gt;</code> <br><br> <code>ByteAddressBuffer</code></td>
            <td><code>t</code></td>
        </tr>
        <tr>
            <td>Unordered Access View (read/write)</td>
            <td><code>RWBuffer&lt;type&gt;</code> <br><br> <code>RWStructuredBuffer&lt;struct&gt;</code> <br><br> <code>RWByteAddressBuffer</code> <br><br> <code>RasterizerOrderedBuffer&lt;type&gt;</code> <br><br> <code>RasterizerOrderedStructuredBuffer&lt;struct&gt;</code> <br><br> <code>RasterizerOrderedByteAddressBuffer</code></td>
            <td><code>u</code></td>
        </tr>
        <!-- BUFFER AS STREAM OUTPUT -->
        <tr>
            <td>Buffer as Stream Output</td>
            <td>-</td>
            <td>-</td>
            <td> </td>
        </tr>
    </tbody>
</table>
