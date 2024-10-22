<script>
    export let data;
    import * as Icons from "$lib/components/Icons.js";

    function getIcon(type) {
        const iconName = type.toUpperCase();
        return Icons[iconName];
    }
</script>

<div class="container">
    {#if getIcon(data.type)}
       <div class="bg {data.type.toLowerCase()}">
          <svelte:component
             this={getIcon(data.type)}
             style="color: white; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 75%; height: 75%; object-fit: cover;"
          />
       </div>
    {/if}
    <h1>{data.title}</h1>
</div>

<style>
.instagram {background: linear-gradient(45deg, #f09433 0%,#e6683c 25%,#dc2743 50%,#cc2366 75%,#bc1888 100%);}
.mail {background: linear-gradient(135deg, #0072ff 0%,#00c6ff 100%);}
.youtube {background: linear-gradient(135deg, #ff0000 0%, #c4302b 100%);}
.tiktok {background: black}
.tumblr {background: linear-gradient(135deg, #36465d 0%, #001935 100%);}
.facebook {background: linear-gradient(135deg, #1877f2 0%, #0f91f3 100%);}
.steam {background: linear-gradient(135deg, #0b1622 0%, #1b2838 100%);}
.github {background: linear-gradient(135deg, #333333 0%, #6e5494 100%);}
.pinterest {background: linear-gradient(135deg, #e60023 0%, #d11919 100%);}
.snapchat {background: linear-gradient(135deg, #ffd900 0%, #ffc800 100%);}
.discord {background: linear-gradient(135deg, #5865F2 0%, #404EED 100%);}
.telegram {background: linear-gradient(135deg, #37aee2 0%, #1e96c8 100%);}
.vsco {background: black}
.doncezart {background: black}

.container{
    width: 64px;  /* Parent is responsive */
    height: auto;
    box-sizing: border-box;
}

.bg{
    border-radius: 16px;
    margin: 8px;
    box-sizing: border-box;
    width: calc(100% - 16px);
    padding-top: calc(100% - 16px);
    position: relative;
}
h1{
    font-size: 12px;
    text-align: center;
    color: white;
    font-weight: 500;
}
@media (max-width: 500px){
        .container{
            width: 100%
        }
        h1{
            font-size: 10px;
        }
    }
</style>