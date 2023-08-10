# 𝗡𝗴𝗶𝗻𝘅/𝗣𝗛𝗣-𝗙𝗣𝗠/𝗠𝘆𝗦𝗤𝗟 𝗯𝘂𝗻𝗱𝗹𝗲 𝗰𝗼𝗻𝗳𝗶𝗴𝘂𝗿𝗲𝗱 𝗳𝗼𝗿 𝘂𝘀𝗶𝗻𝗴 𝘄𝗶𝘁𝗵 𝗗𝗼𝗰𝗸𝗲𝗿 𝗰𝗼𝗻𝘁𝗮𝗶𝗻𝗲𝗿𝘀 𝘁𝗼 𝗵𝗼𝘀𝘁 𝗮𝗽𝗽𝗹𝗶𝗰𝗮𝘁𝗶𝗼𝗻𝘀 𝗹𝗼𝗰𝗮𝗹𝗹𝘆

- put a project to the `/www/app`;
- update Nginx `/hosts/*.conf` depending on the project structure and its entry-point (path and file);
- add `127.0.0.1 dev.local` to the `/etc/hosts` in the localhost file system;
- run `docker-compose up -d` from the repository root;
- go to `http://dev.local:88`;
