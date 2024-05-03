# DirectX12 Resources Cheatsheet

Table with the most common States for DirectX 12 Resources, with their respectives Resource Views, Shader data structures and register types.

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
            <th>Possible Resource States</th>
            <th>Shader (HLSL)</th>
            <th>Shader Register Type</th>
        </tr>
    </thead>
    <tbody>
        <!-- VERTEX BUFFER -->
        <tr>
            <td>Vertex Buffer</td>
            <td>VBV</td>
            <td><code>D3D12_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER</code></td>
            <td>-</td>
            <td> </td>
        </tr>
        <!-- INDEX BUFFER -->
        <tr>
            <td>Index Buffer</td>
            <td>IBV</td>
            <td><code>D3D12_RESOURCE_STATE_INDEX_BUFFER</code></td>
            <td>-</td>
            <td> </td>
        </tr>
        <!-- TEXTURE -->
        <tr>
            <td rowspan=4>Texture</td>
            <td>SRV (read only)</td>
            <td><code>D3D12_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE</code> <br><br> <code>D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE</code> <br><br> <code>D3D12_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE + D3D12_RESO
URCE_STATE_PIXEL_SHADER_RESOURCE</code></td>
            <td><code>Texture&lt;type&gt;</code></td>
            <td><code>t</code></td>
        </tr>
        <tr>
            <td>UAV (read/write)</td>
            <td><code>D3D12_RESOURCE_STATE_UNORDERED_ACCESS</code></td>
            <td><code>RWTexture&lt;type&gt;</code> <br><br> <code>RasterizerOrderedTexture&lt;type&gt</code></td>
            <td><code>u</code></td>
        </tr>
        <tr>
            <td>RTV</td>
            <td><code>D3D12_RESOURCE_STATE_RENDER_TARGET</code></td>
            <td>-<type></td>
            <td> </td>
        </tr>
        <tr>
            <td>DSV</td>
            <td>Depth/Stencil enabled + write: <br><br> <code>D3D12_RESOURCE_STATE_DEPTH_WRITE</code> <br><br> Depth/Stencil enabled + no-write: <br><br> <code>D3D12_RESOURCE_STATE_DEPTH_READ</code></td>
            <td>-<type></td>
            <td> </td>
        </tr>
        <!-- BUFFER -->
        <tr>
            <td rowspan=3>Buffer</td>
            <td>CBV (read only)</td>
            <td><code>D3D12_RESOURCE_STATE_VERTEX_AND_CONSTANT_BUFFER</code></td>
            <td><code>cbuffer {members}</code> <br><br> <code>tbuffer {members}</code> <br><br> <code>ConstantBuffer&lt;struct&gt;</code></td>
            <td><code>b</code></td>
        </tr>
        <tr>
            <td>SRV (read only)</td>
            <td><code>D3D12_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE</code> <br><br> <code>D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE</code> <br><br> <code>D3D12_RESOURCE_STATE_NON_PIXEL_SHADER_RESOURCE +
D3D12_RESOURCE_STATE_PIXEL_SHADER_RESOURCE</code></td>
            <td><code>Buffer&lt;type&gt;</code> <br><br> <code>StructuredBuffer&lt;struct&gt;</code> <br><br> <code>ByteAddressBuffer</code></td>
            <td><code>t</code></td>
        </tr>
        <tr>
            <td>UAV (read/write)</td>
            <td><code>D3D12_RESOURCE_STATE_UNORDERED_ACCESS</code></td>
            <td><code>RWBuffer&lt;type&gt;</code> <br><br> <code>RWStructuredBuffer&lt;struct&gt;</code> <br><br> <code>RWByteAddressBuffer</code> <br><br> <code>RasterizerOrderedBuffer&lt;type&gt;</code> <br><br> <code>RasterizerOrderedStructuredBuffer&lt;struct&gt;</code> <br><br> <code>RasterizerOrderedByteAddressBuffer</code></td>
            <td><code>u</code></td>
        </tr>
        <!-- BUFFER AS STREAM OUTPUT -->
        <tr>
            <td>Buffer as Stream Output</td>
            <td>SOV</td>
            <td><code>D3D12_RESOURCE_STATE_STREAM_OUT</code></td>
            <td>-</td>
            <td> </td>
        </tr>
    </tbody>
</table>

Full list of Resource States: https://docs.microsoft.com/en-us/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_states

## Register Types used in Shaders (HLSL) for Resources

- `b` (e.g. `b0`, `b1`...): registers for Constant Buffers (CBVs)
- `t` (e.g. `t0`, `t1`...): registers for read-only Textures and Buffers (SRVs)
- `u` (e.g. `u0`, `u1`...): registers for read/write Textures and Buffers (UAVs)
- `s` (e.g. `s0`, `s1`...): registers for Samplers
- DirectX 12 also has the conceps of `space` (e.g. `space0`, `space1`, ...). So one resource can be assigned to `(t0, space0)` and another in `(t0, space1)` and they won't collide.
