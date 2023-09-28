<!--
 * @Description:
 * @Version: 1.0
 * @Autor: dudedu
 * @Date: 2023-03-10 17:32:49
 * @LastEditors: dudedu
 * @LastEditTime: 2023-06-13 16:45:49
-->
<template>
  <div id="screen" class="full base-width__paved">
    <div id="noVNC_fallback_error" class="noVNC_center">
      <div>
        <div>noVNC encountered an error:</div>
        <br />
        <div id="noVNC_fallback_errormsg" />
      </div>
    </div>

    <!-- noVNC Control Bar -->
    <div id="noVNC_control_bar_anchor" class="noVNC_vcenter">
      <div id="noVNC_control_bar">
        <div id="noVNC_control_bar_handle" title="Hide/Show the control bar">
          <div />
        </div>

        <div class="noVNC_scroll">
          <h1 class="noVNC_logo" translate="no">OpenEDA</h1>

          <!-- Drag/Pan the viewport -->
          <img
            id="noVNC_view_drag_button"
            type="image"
            alt="Drag"
            src="@/views/remoteDestop/components/novnc/app/images/drag.svg"
            class="noVNC_button noVNC_hidden"
            title="Move/Drag Viewport"
          />

          <!--noVNC Touch Device only buttons-->
          <div id="noVNC_mobile_buttons">
            <img
              id="noVNC_keyboard_button"
              type="image"
              alt="Keyboard"
              src="@/views/remoteDestop/components/novnc/app/images/keyboard.svg"
              class="noVNC_button"
              title="Show Keyboard"
            />
          </div>

          <!-- Extra manual keys -->
          <img
            id="noVNC_toggle_extra_keys_button"
            type="image"
            alt="Extra keys"
            src="@/views/remoteDestop/components/novnc/app/images/toggleextrakeys.svg"
            class="noVNC_button"
            title="Show Extra Keys"
          />
          <div class="noVNC_vcenter">
            <div id="noVNC_modifiers" class="noVNC_panel">
              <img
                id="noVNC_toggle_ctrl_button"
                type="image"
                alt="Ctrl"
                src="@/views/remoteDestop/components/novnc/app/images/ctrl.svg"
                class="noVNC_button"
                title="Toggle Ctrl"
              />
              <img
                id="noVNC_toggle_alt_button"
                type="image"
                alt="Alt"
                src="@/views/remoteDestop/components/novnc/app/images/alt.svg"
                class="noVNC_button"
                title="Toggle Alt"
              />
              <img
                id="noVNC_toggle_windows_button"
                type="image"
                alt="Windows"
                src="@/views/remoteDestop/components/novnc/app/images/windows.svg"
                class="noVNC_button"
                title="Toggle Windows"
              />
              <img
                id="noVNC_send_tab_button"
                type="image"
                alt="Tab"
                src="@/views/remoteDestop/components/novnc/app/images/tab.svg"
                class="noVNC_button"
                title="Send Tab"
              />
              <img
                id="noVNC_send_esc_button"
                type="image"
                alt="Esc"
                src="@/views/remoteDestop/components/novnc/app/images/esc.svg"
                class="noVNC_button"
                title="Send Escape"
              />
              <img
                id="noVNC_send_ctrl_alt_del_button"
                type="image"
                alt="Ctrl+Alt+Del"
                src="@/views/remoteDestop/components/novnc/app/images/ctrlaltdel.svg"
                class="noVNC_button"
                title="Send Ctrl-Alt-Del"
              />
            </div>
          </div>

          <!-- Shutdown/Reboot -->
          <img
            id="noVNC_power_button"
            type="image"
            alt="Shutdown/Reboot"
            src="@/views/remoteDestop/components/novnc/app/images/power.svg"
            class="noVNC_button"
            title="Shutdown/Reboot..."
          />
          <div class="noVNC_vcenter">
            <div id="noVNC_power" class="noVNC_panel">
              <div class="noVNC_heading">
                <img
                  alt=""
                  src="@/views/remoteDestop/components/novnc/app/images/power.svg"
                />
                Power
              </div>
              <input
                id="noVNC_shutdown_button"
                type="button"
                value="Shutdown"
              />
              <input id="noVNC_reboot_button" type="button" value="Reboot" />
              <input id="noVNC_reset_button" type="button" value="Reset" />
            </div>
          </div>

          <!-- Clipboard -->
          <img
            id="noVNC_clipboard_button"
            type="image"
            alt="Clipboard"
            src="@/views/remoteDestop/components/novnc/app/images/clipboard.svg"
            class="noVNC_button"
            title="Clipboard"
          />
          <div class="noVNC_vcenter">
            <div id="noVNC_clipboard" class="noVNC_panel">
              <div class="noVNC_heading">
                <img
                  alt=""
                  src="@/views/remoteDestop/components/novnc/app/images/clipboard.svg"
                />
                Clipboard
              </div>
              <textarea id="noVNC_clipboard_text" rows="5" />
            </div>
          </div>

          <!-- Toggle fullscreen -->
          <img
            id="noVNC_fullscreen_button"
            type="image"
            alt="Full Screen"
            src="@/views/remoteDestop/components/novnc/app/images/fullscreen.svg"
            class="noVNC_button noVNC_hidden"
            title="Full Screen"
          />

          <!-- Settings -->
          <img
            id="noVNC_settings_button"
            type="image"
            alt="Settings"
            src="@/views/remoteDestop/components/novnc/app/images/settings.svg"
            class="noVNC_button"
            title="Settings"
          />
          <div class="noVNC_vcenter">
            <div id="noVNC_settings" class="noVNC_panel">
              <div class="noVNC_heading">
                <img
                  alt=""
                  src="@/views/remoteDestop/components/novnc/app/images/settings.svg"
                />
                Settings
              </div>
              <ul>
                <li>
                  <label
                    ><input id="noVNC_setting_shared" type="checkbox" /> Shared
                    Mode</label
                  >
                </li>
                <li>
                  <label
                    ><input id="noVNC_setting_view_only" type="checkbox" /> View
                    Only</label
                  >
                </li>
                <li>
                  <hr />
                </li>
                <li>
                  <label
                    ><input id="noVNC_setting_view_clip" type="checkbox" /> Clip
                    to Window</label
                  >
                </li>
                <li>
                  <label for="noVNC_setting_resize">Scaling Mode:</label>
                  <select id="noVNC_setting_resize" name="vncResize">
                    <option value="remote">Remote Resizing</option>
<!--                    <option value="off">None</option>-->
<!--                    <option value="scale">Local Scaling</option>-->
                  </select>
                </li>
                <li>
                  <hr />
                </li>
                <li>
                  <div class="noVNC_expander">Advanced</div>
                  <div>
                    <ul>
                      <li>
                        <label for="noVNC_setting_quality">Quality:</label>
                        <input
                          id="noVNC_setting_quality"
                          type="range"
                          min="0"
                          max="9"
                          value="6"
                        />
                      </li>
                      <li>
                        <label for="noVNC_setting_compression"
                          >Compression level:</label
                        >
                        <input
                          id="noVNC_setting_compression"
                          type="range"
                          min="0"
                          max="9"
                          value="2"
                        />
                      </li>
                      <li>
                        <hr />
                      </li>
                      <li>
                        <label for="noVNC_setting_repeaterID"
                          >Repeater ID:</label
                        >
                        <input
                          id="noVNC_setting_repeaterID"
                          type="text"
                          value=""
                        />
                      </li>
                      <li>
                        <div class="noVNC_expander">WebSocket</div>
                        <div>
                          <ul>
                            <li>
                              <label
                                ><input
                                  id="noVNC_setting_encrypt"
                                  type="checkbox"
                                />
                                Encrypt</label
                              >
                            </li>
                            <li>
                              <label for="noVNC_setting_host">Host:</label>
                              <input id="noVNC_setting_host" />
                            </li>
                            <li>
                              <label for="noVNC_setting_port">Port:</label>
                              <input id="noVNC_setting_port" type="number" />
                            </li>
                            <li>
                              <label for="noVNC_setting_path">Path:</label>
                              <input
                                id="noVNC_setting_path"
                                type="text"
                                value="websockify"
                              />
                            </li>
                          </ul>
                        </div>
                      </li>
                      <li>
                        <hr />
                      </li>
                      <li>
                        <label
                          ><input
                            id="noVNC_setting_reconnect"
                            type="checkbox"
                          />
                          Automatic Reconnect</label
                        >
                      </li>
                      <li>
                        <label for="noVNC_setting_reconnect_delay"
                          >Reconnect Delay (ms):</label
                        >
                        <input
                          id="noVNC_setting_reconnect_delay"
                          type="number"
                        />
                      </li>
                      <li>
                        <hr />
                      </li>
                      <li>
                        <label
                          ><input id="noVNC_setting_show_dot" type="checkbox" />
                          Show Dot when No Cursor</label
                        >
                      </li>
                      <li>
                        <hr />
                      </li>
                      <!-- Logging selection dropdown -->
                      <li>
                        <label
                          >Logging:
                          <select
                            id="noVNC_setting_logging"
                            name="vncLogging"
                          />
                        </label>
                      </li>
                    </ul>
                  </div>
                </li>
                <li class="noVNC_version_separator">
                  <hr />
                </li>
                <li class="noVNC_version_wrapper">
                  <span>Version:</span>
                  <span class="noVNC_version" />
                </li>
              </ul>
            </div>
          </div>

          <!-- Connection Controls -->
          <img
            id="noVNC_disconnect_button"
            type="image"
            alt="Disconnect"
            src="@/views/remoteDestop/components/novnc/app/images/disconnect.svg"
            class="noVNC_button"
            title="Disconnect"
          />
        </div>
      </div>
    </div>
    <!-- End of noVNC_control_bar -->

    <div id="noVNC_hint_anchor" class="noVNC_vcenter">
      <div id="noVNC_control_bar_hint" />
    </div>

    <!-- Status Dialog -->
    <div id="noVNC_status" />

    <!-- Connect button -->
    <div class="noVNC_center">
      <div id="noVNC_connect_dlg">
        <div class="noVNC_logo" translate="no">OpenEDA</div>
        <div id="noVNC_connect_button">
          <div>
            <img
              alt=""
              src="@/views/remoteDestop/components/novnc/app/images/connect.svg"
            />
            Connect
          </div>
        </div>
      </div>
    </div>

    <!-- Server Key Verification Dialog -->
    <div class="noVNC_center noVNC_connect_layer">
      <div id="noVNC_verify_server_dlg" class="noVNC_panel">
        <form>
          <div class="noVNC_heading">Server identity</div>
          <div>
            The server has provided the following identifying information:
          </div>
          <div id="noVNC_fingerprint_block">
            <b>Fingerprint:</b>
            <span id="noVNC_fingerprint" />
          </div>
          <div>
            Please verify that the information is correct and press "Approve".
            Otherwise press "Reject".
          </div>
          <div>
            <input
              id="noVNC_approve_server_button"
              type="submit"
              value="Approve"
              class="noVNC_submit"
            />
            <input
              id="noVNC_reject_server_button"
              type="button"
              value="Reject"
              class="noVNC_submit"
            />
          </div>
        </form>
      </div>
    </div>

    <!-- Password Dialog -->
    <div class="noVNC_center noVNC_connect_layer">
      <div id="noVNC_credentials_dlg" class="noVNC_panel">
        <form>
          <div class="noVNC_heading">Credentials</div>
          <div id="noVNC_username_block">
            <label for="noVNC_username_input">Username:</label>
            <input id="noVNC_username_input" />
          </div>
          <div id="noVNC_password_block">
            <label for="noVNC_password_input">Password:</label>
            <input id="noVNC_password_input" type="password" />
          </div>
          <div>
            <input
              id="noVNC_credentials_button"
              type="submit"
              value="Send Credentials"
              class="noVNC_submit"
            />
          </div>
        </form>
      </div>
    </div>

    <!-- Transition Screens -->
    <div id="noVNC_transition">
      <div id="noVNC_transition_text" />
      <div>
        <input
          id="noVNC_cancel_reconnect_button"
          type="button"
          value="Cancel"
          class="noVNC_submit"
        />
      </div>
      <div class="noVNC_spinner" />
    </div>

    <!-- This is where the RFB elements will attach -->
    <div id="noVNC_container">
      <!-- Note that Google Chrome on Android doesn't respect any of these,
           html attributes which attempt to disable text suggestions on the
           on-screen keyboard. Let's hope Chrome implements the ime-mode
           style for example -->
      <textarea
        id="noVNC_keyboardinput"
        autocapitalize="off"
        autocomplete="off"
        spellcheck="false"
        tabindex="-1"
      />
    </div>
  </div>
  <!-- noVNC Control Bar -->
</template>
<script lang="ts">
import { reactive, toRefs } from 'vue';
// import UI from './js/ui';

export default {
  setup() {
    const state = reactive({
      name: '11111',
    });

    onMounted(() => {
      // UI.start(); // 初始化
      // UI.connect(); // 启动远程连接
    });

    return {
      ...toRefs(state),
    };
  },
};
</script>

<style scoped lang="scss">
@import './app/styles/base.css';
@import './app/styles/input.css';

#screen {
  height: calc(100% - 2px);
}
</style>
