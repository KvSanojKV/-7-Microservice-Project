FROM ruby:3.3-slim

WORKDIR /app

# Install dependencies required to build native Ruby gems
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

COPY Gemfile Gemfile.lock ./

RUN bundle install

COPY . .

EXPOSE 8086

CMD ["bundle", "exec", "ruby", "app.rb"]
