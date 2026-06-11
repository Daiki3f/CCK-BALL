    keymap {
        compatible = "zmk,keymap";

        QWERTY {
            bindings = <
&kp ESC           &kp N1        &kp N2        &kp N3      &kp N4     &kp N5  &kp N6  &kp N7     &kp N8     &kp N9          &kp N0          &kp BACKSPACE
&kp TAB           &kp Q         &kp W         &kp E       &kp R      &kp T   &kp Y   &kp U      &kp I      &kp O           &kp P           &kp SEMI
&kp CAPSLOCK      &kp A         &kp S         &kp D       &kp F      &kp G   &kp H   &kp J      &kp K      &kp L           &kp MINUS       &kp SQT
&kp LEFT_SHIFT    &kp Z         &kp X         &kp C       &kp V      &kp B   &kp N   &kp M      &kp COMMA  &kp DOT         &kp FSLH        &kp UP_ARROW
&kp LEFT_CONTROL  &kp LEFT_WIN  &kp LEFT_ALT  &lt 2 &kp DELETE  &lt 1 &kp SPACE  &to 1   &mkp MB1   &mkp MB2  &lt 3 &kp RETURN  &kp LEFT_ARROW  &kp DOWN_ARROW  &kp RIGHT_ARROW
            >;

            sensor-bindings = <&inc_dec_kp C_VOL_UP C_VOL_DN &inc_dec_kp PG_UP PG_DN>;
        };

        F_layers {
            bindings = <
&kp F12      &kp F1  &kp F2  &kp F3  &kp F4  &kp F5  &kp F6     &kp F7     &kp F8  &kp F9  &kp F10  &kp F11
&trans       &kp N1  &kp N2  &kp N3  &kp N4  &kp N5  &kp N6     &kp N7     &kp N8  &kp N9  &kp N0   &trans
&trans       &none   &none   &none   &none   &trans  &mkp LCLK  &kp N4     &kp N5  &kp N6  &trans   &trans
&trans       &trans  &trans  &trans  &trans  &none   &kp N0     &kp N1     &kp N2  &kp N3  &none    &trans
&bootloader  &reset  &trans  &trans  &trans  &trans  &to 3      &mkp RCLK  &trans  &trans  &trans   &trans
            >;

            sensor-bindings = <&inc_dec_kp C_VOL_UP C_VOL_DN &inc_dec_kp PG_UP PG_DN>;
        };

        BT_layers {
            bindings = <
&trans       &bt BT_SEL 0    &bt BT_SEL 1  &bt BT_SEL 2  &bt BT_SEL 3  &bt BT_SEL 4  &trans      &trans  &trans  &trans  &trans  &trans
&trans       &trans          &trans        &trans        &trans        &trans        &trans      &trans  &trans  &trans  &trans  &trans
&trans       &bt BT_CLR_ALL  &trans        &trans        &trans        &trans        &trans      &trans  &trans  &trans  &trans  &trans
&trans       &trans          &trans        &bt BT_CLR    &trans        &trans        &bt BT_NXT  &trans  &trans  &trans  &trans  &trans
&trans       &trans          &trans        &trans        &trans        &trans        &trans      &trans  &trans  &trans  &trans  &trans
            >;

            sensor-bindings = <&inc_dec_kp C_VOL_UP C_VOL_DN &inc_dec_kp PG_UP PG_DN>;
        };

        scroll-layers {
            bindings = <
&trans  &trans    &trans    &trans     &trans  &trans  &trans    &trans  &trans  &trans  &trans  &trans
&trans  &trans    &kp UP    &trans     &trans  &trans  &kp HOME  &trans  &trans  &trans  &trans  &trans
&trans  &kp LEFT  &kp DOWN  &kp RIGHT  &trans  &trans  &kp HOME  &kp PG_DOWN  &kp PG_UP  &kp END  &trans  &trans
&trans  &trans    &trans    &trans     &trans  &trans  &trans    &trans  &trans  &trans  &trans  &trans
&trans  &trans    &trans    &trans     &trans  &to 4  &trans    &trans  &trans  &trans  &reset  &bootloader
            >;

            sensor-bindings = <&inc_dec_kp C_VOL_UP C_VOL_DN &inc_dec_kp PG_UP PG_DN>;
        };

        snipe-layers {
            bindings = <
&trans    &trans        &trans        &trans      &trans     &trans  &trans  &trans     &trans     &trans          &trans          &trans
&trans    &kp Q         &kp W         &kp E       &kp R      &kp T   &kp Y   &kp U      &kp I      &kp O           &kp P           &trans
&trans    &kp A         &kp S         &kp D       &lt 3 F    &kp G   &kp H   &kp J      &kp K      &kp L           &kp MINUS       &trans
&trans    &kp Z         &kp X         &kp C       &kp V      &kp B   &kp N   &kp M      &kp COMMA  &kp DOT         &kp FSLH        &trans
&trans  &trans  &trans  &lt 2 &kp DELETE  &lt 1 &kp SPACE  &to 0  &kp RCTRL  &kp RSHIFT  &lt 3 &kp RETURN  &trans  &trans  &trans
            >;

            sensor-bindings = <&scroll_vertical_encoder>,   // 编码器1：上下滚动
                             <&scroll_horizontal_encoder>;  // 编码器2：左右滚动
        };
    };
};