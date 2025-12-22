# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

BizSKY政企信息化脚手架系统202版 (BizSKY Government-Enterprise Informationization Scaffolding System 202 Edition) - A backend-only scaffolding system providing RESTful API endpoints for government enterprise information systems compliant with third-level security protection standards.

### Technology Stack
- **Database**: PostgreSQL
- **API Framework**: PostgREST (auto-generated RESTful APIs from PostgreSQL schema)
- **License**: Apache License 2.0
- **Domain**: Government enterprise information systems with security compliance

### Current State
This is a newly initialized project in early development phase. The repository currently contains only foundation files:
- README.md - Project description in Chinese
- LICENSE - Apache License 2.0
- .gitignore - Standard ignore patterns for compiled artifacts

No source code, build configuration, or database schema has been implemented yet.

## Development Architecture

### Expected Architecture
Based on the PostgreSQL + PostgREST stack, the project will likely follow this architecture:

1. **Database Layer**
   - PostgreSQL database with structured schema
   - Tables designed for government enterprise workflows
   - Security-first design with proper indexing and constraints

2. **API Layer**
   - PostgREST configuration (postgrest.conf)
   - Auto-generated RESTful APIs from database schema
   - JWT authentication and authorization middleware
   - Rate limiting and request validation

3. **Security Compliance**
   - User authentication and role-based access control (RBAC)
   - Audit logging for all operations
   - Data encryption at rest and in transit
   - Compliance with government security standards

### Recommended Directory Structure (to be created)
```
bizsky/
├── sql/                    # Database schema and migrations
│   ├── migrations/        # Migration files
│   └── schema.sql         # Main database schema
├── api/                   # API configurations and middleware
│   ├── postgrest.conf     # PostgREST configuration
│   └── auth/              # Authentication JWT secrets
├── docs/                  # Documentation
│   ├── api.md            # API documentation
│   └── deployment.md     # Deployment guide
└── docker/               # Docker configuration
    ├── docker-compose.yml
    └── Dockerfile
```

## Development Commands

### Database Operations (to be implemented)
```bash
# Create new database migration
cp sql/migrations/XXXX_migration_name.sql sql/migrations/$(date +%Y%m%d%H%M%S)_migration_name.sql

# Apply database migrations
psql -d bizsky -f sql/migrations/XXXX_migration_name.sql

# Generate PostgREST schema
curl -X POST http://localhost:3000/rpc/refresh_schema
```

### Development Server (to be implemented)
```bash
# Start PostgreSQL with Docker
docker-compose up -d postgres

# Start PostgREST
docker-compose up -d postgrest

# Monitor logs
docker-compose logs -f postgrest
```

### Testing (to be implemented)
```bash
# Run API tests
curl http://localhost:3000/rpc/health_check

# Test specific endpoints
curl http://localhost:3000/profile
```

## Security Considerations

### Government Enterprise Requirements
- All user data must be encrypted at rest
- Implement proper audit logging for all data modifications
- Use JWT tokens with short expiration times
- Implement rate limiting to prevent abuse
- All API endpoints must authenticate and authorize requests

### Database Security
- Use SSL connections for database communication
- Implement proper user roles and permissions
- Regular security audits and vulnerability scanning
- Data backup and disaster recovery procedures

## Configuration Files (to be created)

### postgrest.conf
```ini
db-uri = "postgres://user:pass@localhost:5432/bizsky"
db-schemas = "public"
db-anon-role = "anon"
server-port = 3000
jwt-secret = "your-jwt-secret-here"
```

### Environment Variables
Create `.env` file with:
```
DATABASE_URL=postgres://user:pass@localhost:5432/bizsky
JWT_SECRET=your-jwt-secret-here
PORT=3000
```

## Git Workflow

- Branch from `main` for new features
- Create meaningful commit messages in Chinese or English
- Include database migrations in version control
- Document API changes in API documentation

## Notes for Development

1. **Database First**: Design PostgreSQL schema before implementing APIs
2. **Security First**: Always consider security implications for government systems
3. **Documentation**: Keep API documentation updated with all changes
4. **Testing**: Test all API endpoints thoroughly before deployment
5. **Compliance**: Ensure all features meet government security requirements

## Remote Repository

- Origin: `git@github.com:SimonBizsky/BizSKY.git`
- Main branch: `main`
- Use Git LFS for large binary files if needed