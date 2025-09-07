#include QMK_KEYBOARD_H
#include "keymap_german.h"


// Each layer gets a name for readability, which is then used in the keymap matrix below.
// The underscores don't mean anything - you can have a layer called STUFF or any other name.
// Layer names don't all need to be of the same length, obviously, and you can also skip them
// entirely and just use numbers.
enum layer_names {
    LETTERS,
    CHLAYER,
    SYMBOLS,
    NUMBERS,
    NAVIGAT,
    UMLAUTE,
};

// DEFINE all the key combination and mod tap shit
#define CHLA LT(CHLAYER, KC_TAB)
#define MODD_A GUI_T(KC_A)
#define MODD_R ALT_T(KC_R)
#define MODD_S SFT_T(KC_S)
#define MODD_T CTL_T(KC_T)
#define MODD_N CTL_T(KC_N)
#define MODD_E SFT_T(KC_E)
#define MODD_I ALT_T(KC_I)
#define MODD_O GUI_T(KC_O)
#define BACKK TO(LETTERS)
#define SYM TO(SYMBOLS)
#define NUM TO(NUMBERS)
#define NAV TO(NAVIGAT)
#define UML TO(UMLAUTE)

// DEFINE MEDIA KEYS TO SHORTEN SHIT
#define MSTOP KC_MEDIA_STOP
#define MPREV KC_MEDIA_PREV_TRACK
#define MNEXT KC_MEDIA_NEXT_TRACK
#define MPLAY KC_MEDIA_PLAY_PAUSE
#define MMUTE KC_AUDIO_MUTE
#define MLOWE KC_AUDIO_VOL_DOWN
#define MRAIS KC_AUDIO_VOL_UP

/*
PREVIOUS OVERRIDES, DID NOT COMPILE ANYMORE, USING GETREUER CUSTOM SHIFT NOW

//shift-backspace = DEL
//shift-space = CAPSLOCK
const key_override_t delete_key_override = ko_make_basic(MOD_MASK_SHIFT, KC_BSPC, KC_DEL);
const key_override_t space_key_override = ko_make_basic(MOD_MASK_SHIFT, KC_SPC, KC_CAPS);
a
// This globally defines all key overrides to be used
const key_override_t *key_overrides[] = {
	&delete_key_override,
    space_key_override
};
*/

// HISTORICAL CUSTOM SHIFT

const custom_shift_key_t custom_shift_keys[] = {
  {KC_BSPC , KC_DEL}, // shift-backspace = DEL
  {KC_SPC, KC_CAPS}, // shift-space = CAPSLOCK
};

uint8_t NUM_CUSTOM_SHIFT_KEYS =
    sizeof(custom_shift_keys) / sizeof(custom_shift_key_t);

const uint16_t PROGMEM keymaps[][MATRIX_ROWS][MATRIX_COLS] = {


/* COLEMAKH-DHM, SUCKERS
 *
 * ,-----------------------------------------.           ,-----------------------------------------.
 *.|      |   Q  |   W  |   F  |   P  |   B  |           |   J  |   L  |   U  |   O  | / ?  |      |
 *.|------+------+------+------+------+------|           |------+------+------+------+------+------+
 *.|      |   A  |   R  |   S  |   T  |   G  |           |   M  |   N  |   E  |   I  |   O  |      |
 *.|------+------+------+------+------+------|           |------+------+------+------+------+------+
 *.|      |   Z  |   X  |   C  |   D  |   V  |           |   K  |   H  | , ;  | . :  | - _  |      |
 * `-----------------------------------------'           `-----------------------------------------'
 *                  ,--------------------.               ,------,-------------.
 *                  |  ESC | SPC  | TAB/ |               |      | BKSPC|      |
 *                  `-------------| MULT |               |ENTER |------+------.
 *                                | MOD  |               |      |
 *                                `------'               `------'
 *           
 */

[LETTERS] = LAYOUT_split_3x6_3(
  KC_NO, KC_Q,   KC_W,   KC_F,   KC_P,   KC_B,         KC_J,   KC_L,   KC_U,    KC_Z,   KC_SLSH, KC_NO, 
  KC_NO, MODD_A, MODD_R, MODD_S, MODD_T, KC_G,         KC_M,   MODD_N, MODD_E,  MODD_I, MODD_O,  KC_NO, 
  KC_NO, KC_Y,   KC_X,   KC_C,   KC_D,   KC_V,         KC_K,   KC_H,   KC_COMM, KC_DOT, DE_MINS, KC_NO, 
                         KC_ESC, KC_SPC, CHLA,         KC_ENT, KC_BSPC,KC_NO
),

/* TEH SWITCHINGU LAYER
 *
 * ,-----------------------------------------.           ,-----------------------------------------.
 *.|      |      |      |      |      |      |           |      |      |      |      |      |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 *.|      |      |      | UML  | NUM  |      |           |      | SYM  | NAV  |      |      |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 * |      |      |      |      |      |      |           |      |      |      |      |      |      |
 * `-----------------------------------------'           `-----------------------------------------'
 *                      ,--------------------.    ,------,-------------.
 *                      |      |      |      |    |      |      |      |
 *                      `-------------|      |    |      |------+------'
 *                                    |      |    |      |
 *                                    `------'    `------'
 */
[UMLAUTE] =  LAYOUT_split_3x6_3(
   KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,        KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,
   KC_NO,  KC_NO,  KC_NO,    UML,  NUM,    KC_NO,        KC_NO,    SYM,    NAV,  KC_NO,  KC_NO,  KC_NO,
   KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,        KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,
                           KC_NO,  KC_NO,KC_TRNS,        KC_NO,  KC_NO,  KC_NO
),

/* Symbols
 *
 * ,-----------------------------------------.           ,-----------------------------------------.
 *.|      |   ^  |   "  |   §  |   $  |   %  |           |   &  |   `  |   +  |   *  |   ~  |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 *.|      |   @  |   |  |   \  |   =  |   /  |           |   #  |   (  |   )  |   {  |   }  |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 *.|      |   -  |   '  |   ?  |   !  |   €  |           |      |   [  |   ]  |   <  |   >  |      |
 * `-----------------------------------------'           `-----------------------------------------'
 *                      ,--------------------.    ,------,-------------.
 *                      |      | BACK |      |    |      | BACK |      |
 *                      `-------------|      |    |      |------+------'
 *                                    |      |    |      |
 *                                    `------'    `------'
 */
[SYMBOLS] = LAYOUT_split_3x6_3(
  KC_NO, DE_CIRC, DE_DQUO, DE_SECT,  DE_DLR, DE_PERC,      DE_AMPR, DE_ACUT, DE_PLUS, DE_ASTR, DE_TILD, KC_NO, 
  KC_NO,   DE_AT, DE_PIPE, DE_BSLS,  DE_EQL, DE_SLSH,      DE_HASH, DE_LPRN, DE_RPRN, DE_LCBR, DE_RCBR, KC_NO, 
  KC_NO, DE_MINS, DE_QUOT, DE_QUES, DE_EXLM, DE_EURO,      KC_NO,   DE_LBRC, DE_RBRC, DE_LABK, DE_RABK, KC_NO, 
                             KC_NO,   BACKK,   KC_NO,      KC_NO,   BACKK,   KC_NO
),

/* Numbers
 *
 * ,-----------------------------------------.           ,-----------------------------------------.
 *.|      |  F1  |  F2  |  F3  |  F4  |      |           |   *  |   7  |   8  |   9  |   -  |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 *.|      |  F5  |  F6  |  F7  |  F8  |      |           |   /  |   4  |   5  |   6  |   +  |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 *.|      |  F9  |  F10 |  F11 |  F12 |      |           |      |   1  |   2  |   3  |      |      |
 * `-----------------------------------------'           `-----------------------------------------'
 *                      ,--------------------.    ,------,-------------.
 *                      |      | BACK |      |    |      | BACK |      |
 *                      `-------------|      |    |      |------+------'
 *                                    |      |    |      |
 *                                    `------'    `------'
 */
[NUMBERS] = LAYOUT_split_3x6_3(
    KC_NO, KC_F1,  KC_F2,  KC_F3,  KC_F4, KC_NO,        DE_ASTR, KC_7, KC_8, KC_9, DE_MINS, KC_NO, 
    KC_NO, KC_F5,  KC_F6,  KC_F7,  KC_F8, KC_NO,        DE_SLSH, KC_4, KC_5, KC_6, DE_PLUS, KC_NO, 
    KC_NO, KC_F9, KC_F10, KC_F11, KC_F12, KC_NO,        KC_NO,   KC_1, KC_2, KC_3,   KC_NO, KC_NO, 
                           KC_NO,  BACKK, KC_NO,        KC_NO,   BACKK, KC_NO
),


/* Navigation
 *
 * ,-----------------------------------------.           ,-----------------------------------------.
 *.|      |  ws1 |  ws2 |  ws3 |  ws4 | ws5  |           |      |  INS | HOME | PGUP |      |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 *.|      |  ws6 |  ws7 |  ws8 |  ws9 | ws10 |           | Shift|  Lf  |  Dn  |  Up  |  Rt  |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 * |super | alt  |shift | ctrl |PrnScr|      |           |      |  DEL |  END | PGDN |      |      |
 * `-----------------------------------------'           `-----------------------------------------'
 *                      ,--------------------.    ,------,-------------.
 *                      |      | BACK |      |    |      | BACK |      |
 *                      `-------------|      |    |      |------+------'
 *                                    |      |    |      |
 *                                    `------'    `------'
 */
[NAVIGAT] = LAYOUT_split_3x6_3(
  KC_NO, G(KC_6), G(KC_7), G(KC_8), G(KC_9), G(KC_0),        KC_NO,  KC_INS, KC_HOME, KC_PGUP,   KC_NO, KC_NO, 
  KC_NO, G(KC_1), G(KC_2), G(KC_3), G(KC_4), G(KC_5),      KC_LSFT, KC_LEFT, KC_DOWN,   KC_UP, KC_RGHT, KC_NO, 
  KC_NO, KC_LWIN, KC_LALT, KC_LSFT, KC_LCTL, KC_PSCR,        KC_NO,  KC_DEL,  KC_END, KC_PGDN,   KC_NO, KC_NO, 
                             KC_NO,   BACKK,   KC_NO,        KC_NO,  BACKK,   KC_NO
),

/* Umlaute
 *
 * ,-----------------------------------------.           ,-----------------------------------------.
 *.|      |      |      |      |      |      |           |      |      |  Ü   |      |      |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 *.|      |   Ä  |      |  ß   |      |      |           |      |      |      |      |  Ö   |      |
 * |------+------+------+------+------+------|           |------+------+------+------+------+------|
 * |      |MSTOP |MPREV |MNEXT |MPLAYPAUSE   |           |MMUTE |MLOWER|MRAISE|      |      |      |
 * `-----------------------------------------'           `-----------------------------------------'
 *                      ,--------------------.    ,------,-------------.
 *                      |      | BACK |      |    |      | BACK |      |
 *                      `-------------|      |    |      |------+------'
 *                                    |      |    |      |
 *                                    `------'    `------'
 */
[UMLAUTE] =  LAYOUT_split_3x6_3(
   KC_NO,   KC_NO,  KC_NO,  KC_NO,  KC_NO,  KC_NO,        KC_NO,  KC_NO, DE_UDIA, KC_NO,   KC_NO, KC_NO, 
   KC_NO, DE_ADIA,  KC_NO,  DE_SS,  KC_NO,  KC_NO,        KC_NO,  KC_NO,   KC_NO, KC_NO, DE_ODIA, KC_NO, 
   KC_NO,   MSTOP,  MPREV,  MNEXT,  MPLAY,  KC_NO,        MMUTE,  MLOWE,   MRAIS, KC_NO,   KC_NO, KC_NO, 
                            KC_NO,  BACKK,  KC_NO,        KC_NO,  BACKK,   KC_NO
)};

/*
bool process_record_user(uint16_t keycode, keyrecord_t *record) {
    switch (keycode) {

    case KC_ESC:
        // Detect the activation of only Left Alt
        if (get_mods() == MOD_BIT(KC_LALT)) {
            if (record->event.pressed) {
                // No need to register KC_LALT because it's already active.
                // The Alt modifier will apply on this KC_TAB.
                register_code(KC_TAB);
            } else {
                unregister_code(KC_TAB);
            }
            // Do not let QMK process the keycode further
            return false;
        }
        // Else, let QMK process the KC_ESC keycode as usual
        return true;

    }
    return true;
}
    */


// HISTORICAL CUSTOM SHIFT

bool process_record_user(uint16_t keycode, keyrecord_t* record) {
  if (!process_custom_shift_keys(keycode, record)) { return false; }
  // Your macros ...

  return true;
}