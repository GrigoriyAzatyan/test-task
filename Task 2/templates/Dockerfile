FROM node:latest as build
RUN npm update -g; npx create-next-app next-app --ts --eslint; cd /next-app; yes | npx next build

FROM node:latest as production
WORKDIR /temp
COPY --from=build /next-app .
COPY --from=build /next-app/.next .
WORKDIR /script
COPY fill_code.sh.j2 .
WORKDIR /next-app
EXPOSE 3000
ENTRYPOINT /bin/bash -c /script/fill_code.sh.j2
