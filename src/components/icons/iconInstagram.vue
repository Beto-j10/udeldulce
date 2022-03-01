<script setup>
const props= defineProps({
    size: {
        type: Number,
        required: true,
    },
})
const sizePx = props.size + 'px'
</script>
<template>
    <svg :style="{ width: sizePx, height: sizePx }"
        xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="48" height="48" fill-rule="evenodd" stroke-linejoin="round"
        stroke-miterlimit="1.41421" xmlns:v="https://vecta.io/nano">
        <path d="M22 7a5 5 0 0 0-5-5H7a5 5 0 0 0-5 5v10a5 5 0 0 0 5 5h10a5 5 0 0 0 5-5V7z" fill="url(#A)" />
        <g fill="#fff">
            <path
                d="M14.958 5.005c2.091.02 4.016 1.815 4.037 4.037v5.916c-.02 2.083-1.815 4.016-4.037 4.037H9.042c-2.092-.02-4.016-1.815-4.037-4.037V9.042c.019-2.093 1.81-4.016 4.037-4.037h5.916zm-5.889.945c-1.623.005-3.103 1.412-3.119 3.098v5.904c.015 1.605 1.388 3.082 3.098 3.098h5.904c1.609-.015 3.082-1.388 3.098-3.098V9.048c-.015-1.616-1.415-3.082-3.098-3.098-1.961-.006-3.922 0-5.883 0zm2.955 2.55c1.618.015 3.126 1.263 3.422 2.862.211 1.14-.187 2.376-1.027 3.178a3.57 3.57 0 0 1-3.622.754c-1.386-.507-2.361-1.968-2.296-3.448C8.58 10.078 10.142 8.506 12 8.5h.024zm-.04.947c-1.155.011-2.244.887-2.484 2.025-.243 1.151.419 2.428 1.506 2.887a2.65 2.65 0 0 0 3.293-1.233c.593-1.211.034-2.856-1.218-3.441a2.59 2.59 0 0 0-1.097-.238z"
                fill-rule="nonzero" />
            <path
                d="M16.5 8.227c0-.193-.077-.378-.213-.514s-.321-.213-.514-.213h-.046c-.193 0-.378.077-.514.213S15 8.034 15 8.227v.023c0 .199.079.39.22.53s.331.22.53.22a.75.75 0 0 0 .75-.75v-.023z" />
        </g>
        <defs>
            <radialGradient cx="0" cy="0" gradientTransform="matrix(27.933,0,0,27.933,2,21.5)"
                gradientUnits="userSpaceOnUse" id="A" r="1">
                <stop offset="0" stop-color="#ff8100" />
                <stop offset=".19" stop-color="#ff7209" />
                <stop offset=".32" stop-color="#f55e16" />
                <stop offset=".48" stop-color="#d92938" />
                <stop offset="1" stop-color="#9100ff" />
            </radialGradient>
        </defs>
    </svg>
</template>