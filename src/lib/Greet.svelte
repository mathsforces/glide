<script lang="ts">
  import { invoke } from "@tauri-apps/api/tauri"

  let gitInstallationMessage = "Loading...";
  async function getGitInstallationInfo() {
    if (await invoke("is_git_installed")) {
      gitInstallationMessage = "git is installed!"
    } else {
      gitInstallationMessage = "git is not installed!"
    }
  }
  getGitInstallationInfo()
</script>

<div>
  <p>{gitInstallationMessage}</p>
</div>