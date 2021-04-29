<h4>
  <a href="{{ repository.playbooks }}">Main Playbook</a>
  <span> | </span>
  <a href="{{ profile.galaxy }}/{{ role_name }}">Galaxy</a>
  <span> | </span>
  <a href="{{ repository.group.ansible_roles }}/{{ role_name }}/-/blob/master/CONTRIBUTING.md">Contributing</a>
  <span> | </span>
  <a href="{{ chat_url }}">Chat</a>
  <span> | </span>
  <a href="{{ website.homepage }}">Website</a>
</h4>
<p>
  <a href="{{ repository.group.ansible_roles }}/{{ role_name }}">
    <img alt="Version" src="https://img.shields.io/badge/version-{{ version }}-blue.svg?cacheSeconds=2592000" />
  </a>
  <a href="{{ website.documentation }}/{{ role_name }}" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="{{ repository.gitlab_ansible_roles_group }}/{{ role_name }}/-/raw/master/LICENSE" target="_blank">
    <img alt="License: {{ license }}" src="https://img.shields.io/badge/License-{{ license }}-yellow.svg" />
  </a>
  <a href="https://twitter.com/{{ profile.twitter }}" target="_blank">
    <img alt="Twitter: {{ profile.twitter }}" src="https://img.shields.io/twitter/follow/{{ profile.twitter }}.svg?style=social" />
  </a>
  <a href="">
    <img alt="macOS build status" src="https://img.shields.io/github/checks-status/MegabyteLabs/{{ github_link }}/master?color=cyan&label=macOS%20Build%20Status&logo=apple&style=for-the-badge">
  </a>
  <a href="">
    <img alt="Windows 10 build status" src="https://img.shields.io/github/checks-status/MegabyteLabs/{{ github_link }}/master?color=cyan&label=Windows%20Build%20Status&logo=windows&style=for-the-badge">
  </a>
  <a href="">
    <img alt="Linux build status" src="https://img.shields.io/github/checks-status/MegabyteLabs/{{ github_link }}/master?color=cyan&label=Windows%20Build%20Status&logo=windows&style=for-the-badge">
  </a>
</p>
