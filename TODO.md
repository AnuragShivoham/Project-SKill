# Project-Skill IDE Completion TODO

## Phase 1: Authentication Fixes
- [ ] Fix sign up for new students, mentors, admin roles
- [ ] Ensure role assignment works correctly on sign up
- [ ] Handle email confirmation if needed

## Phase 2: useProjectFiles Hook
- [ ] Rename useFileSystem to useProjectFiles
- [ ] Add importFiles method for local folder upload
- [ ] Add cloneGitHubRepo method with GitHub API integration
- [ ] Add getFileSummary method
- [ ] Update method names to match plan (createNode, deleteNode, etc.)
- [ ] Add lazy loading for large GitHub repos
- [ ] Namespace GitHub clones under /repos/<repo-name>/

## Phase 3: File Operations
- [ ] Implement local file/folder import with drag-drop or file input
- [ ] Add JSZip for ZIP export functionality
- [ ] Update export to create actual ZIP files
- [ ] Add file-saver for downloads

## Phase 4: GitHub Integration
- [ ] Create GitHub API service module
- [ ] Implement repo URL parsing
- [ ] Fetch default branch and recursive tree
- [ ] Fetch file contents with rate limiting
- [ ] Handle large repos and binary files
- [ ] Add clone button to File Explorer

## Phase 5: Terminal Enhancements
- [ ] Implement real command execution (not simulated)
- [ ] Add [EXECUTE] tag parsing in AI chat
- [ ] Enable AI-triggered terminal commands
- [ ] Add command history persistence
- [ ] Improve visual output formatting

## Phase 6: Persistence Options
- [ ] Add Supabase database storage option
- [ ] Allow switching between localStorage and DB
- [ ] Sync files across sessions/devices

## Phase 7: UI Enhancements
- [ ] Add context menu to File Explorer (rename, duplicate, etc.)
- [ ] Improve file operations panel with import/clone buttons
- [ ] Add loading states and error boundaries

## Phase 8: Dependencies & Build
- [ ] Add JSZip, file-saver, octokit (GitHub API) to package.json
- [ ] Update imports and types
- [ ] Ensure TypeScript compilation

## Phase 9: Production & Security
- [ ] Add Vercel deployment config
- [ ] Environment variable handling
- [ ] Security audit and improvements
- [ ] Performance optimizations

## Phase 10: Testing & Validation
- [ ] Test all new features
- [ ] Verify AI integration works
- [ ] Check cross-browser compatibility
- [ ] Validate production build
