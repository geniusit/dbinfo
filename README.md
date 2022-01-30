#install story book
npm i --dev @nrwl/storybook

#create library
npx nx g @nrwl/react:lib ui --directory=shared --style=css

#create component
npx nx g @nrwl/react:component topic-button --project=shared-ui --style=css

#generate story for a specific component
npx nx generate @nrwl/react:storybook-configuration --name=shared-ui --cypressDirectory=storybook-e2e

#launch storybook
npx nx storybook shared-ui

#rerun a storybook generation
nx g @nrwl/react:stories shared-ui

#build a storybook
NODE_ENV=development nx run shared-ui:build-storybook --skip-nx-cache

#run built storybook
npx http-server dist/storybook/shared-ui

#run application
nx serve securify
